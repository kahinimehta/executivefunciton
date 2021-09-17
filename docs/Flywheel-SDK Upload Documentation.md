---
layout: default
title: Flywheel-SDK Upload Documentation
has_children: false
parent: Documentation
has_toc: false
nav_order: 1
---
## Requirements

This upload requires:

  * A local installation of [Python](https://pennlinc.github.io/docs/Basics/python/)
  * [Logging in](https://pennlinc.github.io/docs/flywheel) to Flywheel using the CLI
  * A directory of files to upload to Flywheel
  * A .tsv of SCANID's and BBLID's (optional)

## Getting started

We will be uploading files using the [flywheel-SDK](https://flywheel-io.gitlab.io/product/backend/sdk/branches/master/python/getting_started.html). To get started, import necessary packages and log in using the CLI.

```Python
import glob
import flywheel
fw = flywheel.Client()
```
Set project using its name on flywheel

```Python
EFProj=fw.projects.find_first('label=EFR01')
print(EFProj)
```

Set your directory to location of files for upload and list out files.

```Python
root_dir = '/Users/krmurtha/Box Sync/EXECUTIVE_FUNCTION/SCANNER_TASK/'
bids_dir = 'BIDS/test'
all_files=glob.glob(root_dir + bids_dir + '*/*')
```

## Upload to Session level of Flywheel

To upload to the session or scan level (ie: BIDS files, .zip file of Variability Tasks), iterate through subjects and sessions to access session containers, then pick the corresponding file that matches the session label and upload.

In this example, we use the BIDS file name in a task file to match each .tsv with the appropriate session on flywheel.

```python
subjects=EFProj.subjects() #access all subjects in given project 
sessions=[]
for s in subjects : #loop through subs and access all sessions in a given project 
    tempsessions=s.sessions()
    sessions.extend(tempsessions)

for ses in sessions: #loop through sessions and save scan id
    scanid=ses.label
    for file in all_files:
        f=file.split('/')
            g=(f[len(f)-1]).split('_')
            h=(g[1].split('-'))[1]
            if scanid == h: #match session id to scan id in the file to be uploaded:
                print("uploading {0} to {1}".format(file, scanid))
                ses.upload_file(file)
```
## Upload to the Acquisition level of Flywheel

To upload to the acquisition or sequence level (ie: raw .log files or PMU associated with a specific acquisition), iterate through sessions and acquisitions to select the acquisition label you are looking for, then pick the corresponding file that matches the session label and upload.

For this example, we use scanner task .log files that are uploaded directly to the fracback acquisition, using a .csv of scan id's and bbl id's from oracle.

```python

ids=pd.read_csv('EFR01DataEntryTracke-Eft1scanID_DATA_2021-09-15_1520.csv')
id_dict=dict(zip(ids.bblid, ids.scan_id_timepoint_1))

for ses in sessions: #loop through sessions and save scan id
        sesid=ses.label
        acq=ses.acquisitions()
        for a in acq: #loop through acquisitions for each session
            EFFiles=a.files #access all files attatched to a session (ie: nifti, dicom)
            EFTypes=[x.type for x in EFFiles] #identify type of file
            for file in to_upload1: 
                f=(file.split('/'))
                bblid=f[len(f)-2]
                scanid = id_dict[int(bblid)]
                #search for correct label and file type in acquisition, and match session id to scan id in the file to be uploaded:
                if 'ABCD_fMRI_frac-no-back-run1' in a.label or 'func_task-fracnoback_run-02' in a.label and 'nifti' in EFTypes and int(sesid) == scanid:
                    print('uploading {0} to {1}'.format(file, scanid))
                    a.upload_file(file)
```
