---
layout: default
title: 2022 Data Freeze
has_children: false
parent: Documentation
has_toc: false
nav_order: 12
--- 

# EF April 2022 Data Freeze 
*Prior to Kristin and Sophia's departure in summer 2022, all EF data collected before April 1st, 2022, was downloaded, organized, and saved to Flywheel. This page incluldes details about current enrollment, data organization, auditing, and the final resting place of each data type.

Additional information on data completeness per subject can be found [/here](https://docs.google.com/spreadsheets/d/1DYNd1Qj7Q0s9rEqe1_ezLQwNYcPN44cORnge3UAhqF0/edit#gid=794691291).*

### Current Enrollmentt 
As of April 1st, 2022, 173 parrticipantst had signed the EF consent form and participated in intake procedures under the LiBI Protocol. 119 participants had completed T1 imaging procedures. 37 participants had completed T2 imaging procedures. 

### Data sources 
**Enrollment data** was pulled from the [/EFR01 Data Entry #tracker](https://axis.med.upenn.edu/redcap_v10.3.7/DataEntry/record_status_dashboard.php?pid=378) project on Axis, maintained by the study coordinators. Relevant reports include [ef_t1_scan_ID](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=2258), [ef_t2_scan_ID](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=2597), [/redcap_ids](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=2598), and [/collateral IDs](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=1362). 

**Imaging data** is sourced directly from Flywheel, using [/FlywheelTools](https://fw-heudiconv.readthedocs.io/en/latest/). 

**Task data** is pulled from [/Penn+Box](https://upenn.app.box.com/folder/141611592732) and Flywheel. 

**Raw self report data** is pulled from the [/Common Self-report Scales #collection](https://axis.med.upenn.edu/redcap_v10.3.7/index.php?pid=191) Project on Axis. Scales included in the **main battery** are pulled used  using the [/EF all self reports](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=191&report_id=1318) report. Scales included in the **pre/post scan battery** are pulled using the [/EF STAI S/T](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=191&report_id=1331) report. 

**CNB Data** is pulled from both the [/main WebCNP page](https://webcnp.med.upenn.edu/) and the [/WebCNP survey page](https://webcnp.med.upenn.edu/surveys/). T1 LiBI CNB data can be acccessed using the SiteID "LIBI." T2 LiBI CNB data, as well as all EXECTS battery data, can be accessed using the SiteID "EXECTS." 

**Variability data** is pulled from [/Penn+Box](https://upenn.app.box.com/folder/141610624437). 

**Clinical or Diagnostic data** is pulled from [/Oracle](https://bbldm.pmacs.upenn.edu/), using the Diagnosis Retrieve function for the LiBI Common protocol. 

**Demographic Data** is pulled both from [/Oracle](https://bbldm.pmacs.upenn.edu/), and the [/EFR01 Data Entry #tracker](https://axis.med.upenn.edu/redcap_v10.3.7/DataEntry/record_status_dashboard.php?pid=378) Project on Axis, using the [/Demos](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=1361) report. Age at scan can be calculated by using subject date of birth and date of scan pulled from Flywheel. Current ages, calculated in year and months, are saved on Saturn at the following file path: `afp://saturn/Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/2022_data_freeze/inputs/t1_ages.csv` and `afp://saturn/Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/2022_data_freeze/inputs/t2_ages.csv`

### Uploading Outstanding Data to Flywheel 
Any data that hasn't been uploaded after each individual acquisition can be uploaded in batches. This is especially helpful for the task data, which needs to be scored before it is uploaded. 

1. To score raw task data and convert into a BIDS-valid `.tsv` and `.json`, follow the steps outlined in [/convert_and_score_EF_task_data.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/convert_and_score_EF_task_data.ipynb) 

2. To upload raw task data from PennBox, (ie: `.log ` files) to the acquisition level , follow the steps outlined in [/log_file_atttachment_upload.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/log_file_attachment_upload.ipynb). 

3. To upload scored data from PennBox, (ie: `.json` and `.tsv` files) to the session level, follow tthe steps outlined in [/bids_attachment_upload.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/bids_attachment_upload.ipynb). 

### Self Report Data merges + Organization
The theory behind these data freezes is to add data not included in the previous upload to a cleaned, organized `.csv`. Organiziation of self report scales was last completed in March of 2020, and therefore, scripts in this section will build off of files previously cleaned and currently stored on Saturn, at the following file path: `afp://saturn/Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/flywheel_data_uploads/data_ready_for_upload`. When these steps need to be performed again, for subsequent data freezes, the same scripts can be used, while substituting the current cleaned data that lives on flywheel. 

Records not inculded in previous freezes is identified from the raw data using the RedCap Scales ID, which is tracked manually in the Axis Tracker. The scripts below will use the data in the [/redcap_ids](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=2598) or [/collateral_ids](https://axis.med.upenn.edu/redcap_v10.3.7/DataExport/index.php?pid=378&report_id=1362) reports, to add any new records to a new `.csv`. 

**Note:** none of this data is scored, so as to avoid version contol or batch effects. 

1. To merge and organize pre-scan self reports into one file, follow the steps outlined in [/merge_pre_post_scan_scales.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/merge_pre_post_scan_scales.ipynb). 

2. To merge and organize the main battery of self reports into one file, follow the steps outlined in [/merge_main_scales.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/merge_main_scales.ipynb). 

3. To merge and organize collateral self reports into one file, follow the steps outlined in [\merge_collateral_scales.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/merge_collateral_scales.ipynb).

### Audit Scripts
These scripts follow the same basic logic -- using the enrollment list pulled from Axis, a series of binary spreadsheets are created to determine which measures are complete for which participants, with the goal of filling in this [/google sheet](https://docs.google.com/spreadsheets/d/1DYNd1Qj7Q0s9rEqe1_ezLQwNYcPN44cORnge3UAhqF0/edit#gid=794691291). 

1. To complete an audit of imaging data on Flywheel, first run the `Flaudit` gear on Flywheel. Using both the `bids.csv` and `seqinfo.csv` outputs, follow the steps in [/imaging_audit.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/imaging_audit.ipynb) to fill in the imaging section of the audit spread sheet. 

2. To complete an audit of the ancillary files on Flywheel (task data, variability, etc) follow the steps in [/flywheel_attachment_audit.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/flywheel_attachment_audit.ipynb). This script queries Flywheel directly by using the SDK and CLI. 

3. To complete an audit of the main battery of self report scales, follow the steps in [/main_scales_audit.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/main_scales_audit.ipynb). 

4. To complete an audit of the pre/post scan scales, follow the steps in [/pre_post_scan_scales_audit.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/pre_post_scan_scales_audit.ipynb).

5. To complete an audit of the collateral scales, follow the steps in [/collateral_scales_audit.ipynb](https://github.com/PennLINC/executivefunction/blob/master/datafreeze_notebooks/collateral_scales_audit.ipynb).