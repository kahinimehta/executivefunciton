---
layout: default
title:  Post Scan
has_children: false
parent: Documentation
has_toc: false
nav_order: 5
--- 

# Post Visit Admin
{: .no_toc }
* TOC
{:toc}

## Data Storage
1. [Flywheel](https://upenn.flywheel.io/): 
- Navigate to Flywheel and sign in with your UPenn credentials. 
- Select the EFR01 Project→ then select “Sessions”. 
- All MRI series should appear on Flywheel because you added the Flywheel Study Comment prior to scan administration. When the data first appears on flywheel it will look like the picture below:
<img src="/executivefunction/assets/images/EF41.png" alt="Flywheel1">

- **Timepoint 1**: 
1. Select the scan that you just completed, click “Subject” → Copy the ScanID portion of the Label, then delete from the label to leave only the BBLID → select “Human” → Click “Save”
2. Next, select “Session” → Delete “BRAIN Research ^Satterthwait” Label, and paste the ScanID → Press Save
 <img src="/executivefunction/assets/images/EF42.png" alt="Flywheel2">   

- **Timepoint 2**: Linking to first timepoint
1. Select the blue check mark under “Action” to select the scan → select Action drop down → Select “Move Scan to Existing Subject” → Fill in the information as seen below, select the participant’s BBL ID from the list → hit save – this will remove the ScanID from the Subject Label
 <img src="/executivefunction/assets/images/EF43.png" alt="Flywheel3">  

2. Next, Select Session → Delete the Brain research label and insert the Scan ID for the scan you just completed → hit save 
3. Deleting duplicates- If you had to rerun any sequence of the scan due to motion or some other error, delete the “incorrect” data from flywheel by selecting the NIFTI only and clicking the trash button.
4. Running [Fw-Heudiconv Curation](https://fw-heudiconv.readthedocs.io/en/latest/)
    - This is done to convert data to BIDs form (see Tinshe’s documentation HERE for information on BIDs and how to set this up on your computer)
    - After renaming the scan on Flywheel (above) open up a new terminal window
    - Enter “conda activate flywheel”
    - Navigate to where you have stored the fw-heudiconv heuristic file (this is an example) 
    - Enter ```cd Desktop/Informatics/Flywheel_Curation/Projects/EFR01/```
    - Select the scan that you would like to convert by entering the follow command (XXXXX = enter scan/session ID) 
    ```fw-heudiconv-curate --project EFR01  --heuristic EF_heuristic20200819.py --session XXXXX```
    
    This should prompt this message 

    ```INFO: =================: fw-heudiconv curator starting up :=================```

    ```INFO: Loading heuristic file...```

<img src="/executivefunction/assets/images/fw-hcv.png" alt="Heudiconv">  

_NOTE: All Data (Task, Variability, Self Reports) final resting place is on Flywheel_

## Variability/Task File Back Up: 
Variability and the scanner task should be stored on both PennBox and the orange backup drive stored in the Purple room of Gates
# update

## AppointmentPlus: 
Update status to completed

## AxisTracker: 
Navigate to [https://axis.med.upenn.edu/index.php](https://axis.med.upenn.edu/index.php) project titled: **EFR01 Data Entry #tracker** → Select “Add/Edit Record” on the left-side panel,  enter BBL in “Enter a new or Existing REDCap ID” → update admin and corresponding Scan Visit page

## Procedure Update: 
Update scan notes on Oracle by selecting “Procedures” on the left hand side → “Procedure Update” search by BBL and fill out the information in accordance with the picture below
<img src="/executivefunction/assets/images/EF44.png" alt="IMG Update">  

_Note: include any scan notes in “Scan Notes” section in axis EF data tracker_ 

## Miscellaneous: 
1. Update google sheet EF Tracker
2. CNB Update: Update admin notes: update notes by going to [https://webcnp.med.upenn.edu/](https://webcnp.med.upenn.edu/) >> View results/scores >> searching by BBLID and then entering comments 
3. Study Enroll Update: On oracle, select “Study_Enroll” on left-side panel, select “StudyEnroll Update” and change study status to “in follow-up” and save
4. Update recruitment spreadsheet: mark participant as “1” under completed and consented
5. Consents: make sure to download consents from axis and save them here (afp://Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/VIRTUAL EF ASSESSMENTS/CONSENTS/)
6. Payments: Update travel and print receipts for clincard report



