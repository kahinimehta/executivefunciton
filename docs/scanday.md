---
layout: default
title: Scan Day Protocol/ MRI Visits
has_children: false
parent: Documentation
has_toc: false
nav_order: 8
--- 

# Scan Day Protocol/ MRI Visits (work in progress)

## Pre-visit procedures
### EPIC Order/Generating an MRN on PennChart
1. Search for research participant using: **MRN or Full Name and Date of Birth**. If they do not already exist in PennChart system, click “New” and fill out “Demographics” page with their address and emergency contact
<img src="/executivefunction/assets/images/EF10.png" alt="Search for participant"> 

2. Enter **study code** (IRB Number) or **RBN** in “Research Studies” search bar. Press enter, or click the **green plus sign** to “add.”
<img src="/executivefunction/assets/images/EF11.png" alt="Research studies"> 

3. In the participant information page: 
    - Mark **status** as “Consented/Enrolled” (1060)
    - Leave **coordinator** field and **participant ID** field blank
    - Enter the participant’s scheduled visit date in **both start and end date** fields. 
    _**Note**: this will allow you to avoid all non-study charges being sent to your queue for billing review, only charges that may be associated with your study_
    - Click **accept**
<img src="/executivefunction/assets/images/EF12.png" alt="Study status"> 

### Creating MRI Encounter and Associating a Research Study:
1.	Click **Encounters** in top menu bar, and select **Encounter** from dropdown menu. 
<img src="/executivefunction/assets/images/EF13.png" alt="Encounters"> 

2. Type “=” to auto-populate information from most recent patient search, or select from **Open Patients** section at the bottom of the popup. 
<img src="/executivefunction/assets/images/EF14.png" alt="Open patients"> 

3. Click **New** within patient encounter record. 
<img src="/executivefunction/assets/images/EF15.png" alt="New"> 

4. Within the **New Encounter** popup, enter the following information:
- Type= research noncharable
- Provider= your PI or relevant MD
    - Ted Satterthwaite
    - Dan Wolf
    - Christian Kohler
    - Raquel Gur 
- Department= 423 (PBH HUP Gates) 
<img src="/executivefunction/assets/images/EF16.png" alt="Encounter"> 

5. Click the **Add Order** button in the lower left corner of the screen, and type **70551**. 
<img src="/executivefunction/assets/images/EF17.png" alt="Add order">

6. Click **Database** tab, From the popup menu, select **MR Head WO IV Contrast** (IMGMR0061). 
<img src="/executivefunction/assets/images/EF18.png" alt="Database">

7. Enter the following information in the procedure order popup:
    - Pregnant (if applicable): **NO**
    - Pacemaker or ICD: **NO**
    - Metallic or electronic implants or devices: **NO**
    - **Expected date: date of MRI**
    - Reason for exam: type **Research**
    - Storage: leave blank
    - Responsible Party: select **Personal/Family**
    - Class: select **Radiology**
    - Priority: select **Routine**
<img src="/executivefunction/assets/images/EF19.png" alt="Order">

8. Enter **SmartText** into Comments field 
    - Service Center: CAMRIS
    - Billing Code: IRB# 
    - MRHDUC
    - Modifiers: RES, BSA, 265
    - Resource Code: HUP6
    - Dept:423
    - Ordering Physician: [MD listed on encounter] 
    - CRC Contact: [Study Coordinator and phone number] 
    - Requested Date of MRI 
    - Requested Time of MRI
<img src="/executivefunction/assets/images/EF20.png" alt="Order details">

9. CC Results to ordering physician
10. Add modifiers:
- RES (“Radiology Service Center”)
- BSA (“Bill to Study”)
- 265 (“Research No Scheduling Ticket”)
11. Enter “research” in field labeled “Reason for Exam”
12. Close out imaging popup
13. Associate ICD Diagnosis
- Click on Dx Association in order popup in right-corner 
<img src="/executivefunction/assets/images/EF21.png" alt="Dx">

- Type in z00.6 to the empty field and select any option from the populated list. 
<img src="/executivefunction/assets/images/EF22.png" alt="z00.6">

- Check both boxes to associate dx 
<img src="/executivefunction/assets/images/EF23.png" alt="associate dx">

14. Associate research study
- In the “Options” tab on the order tab, click “Research Association”
<img src="/executivefunction/assets/images/EF24.png" alt="Research association">
- Check box associated with appropriate study and click “accept”
<img src="/executivefunction/assets/images/EF25.png" alt="Research association acceptance">

15. On the left-hand side click “follow up” on the right side fill out PI’s name to route it directly to PI and then click on the unsigned order again and select “pend order”
16. Email Ted letting them know there is an order waiting to be signed
17. Next, go to the order page and copy the order confirmation #, add this # to the “Order #” field on the CAMRIS calendar and the appointment should go from light to dark green

### RADIOLOGY SCHEDULING
1. Call 215-662-3000, type 1 
2. Say “I’d like to schedule an MRI for research”
3. Provide patient: (a) MRN, (b) Date of Birth, (c) height/weight
Note: participant MRN’s can be found on Saturn, titled “MRN2020NEW_3” (Saturn/Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/NewMRNs)
Location: HUP6 (Founders Basement 2, FNDBAMR2), date/time of scan
4. Go through medical screener again
5. For T1→ ask to put in demographic information and supply information about parents, address, race, ethnicity, preferred language
Note: make sure scan is being billed to research

### GENERATING SCAN ID
1. Log into Oracle and go to “Procedures” on the left-hand side
2. Select: “Procedure Store” → “IMG Store” and fill out the relevant information (see image below) and click save. Record generated procedure ID.
Note: Visit # will be used to indicate whether scan is @ T1/2/3, for timepoint 1 scan visit #=1
Note: click the green check next to BBLID each time to ensure you are selecting the correct BBL
<img src="/executivefunction/assets/images/EF26.png" alt="Scan ID generation">

### Generating Self-Reports: INITIATING SELF-REPORT SCALES IN ORACLE-REDCAP
*Note: In order to generate SR scales, they must be enrolled in EF (this should have been completed during intake CAPA, if not, see below for study-enroll procedures)*
*For issues troubleshooting Redcap contact Sage Rush or Scott Troyan

1. Log into Oracle and go to “REDCAP_SELFREPORT” on the left-hand side
2. Select: “Subject SelfR Store” and fill out relevant information (see image below)
<img src="/executivefunction/assets/images/EF27.png" alt="SR store">

*Reminder: subject must be enrolled in study to activate their scales in redcap*
3. If there is a collateral tied to the subject (and collateral scales) you will enter the collateral ID that is autogenerated on this page at the bottom of the screen. 
4. Select enter and you will receive a “SCALEID” and a “REDCapID”.
    - You can use either one of these IDs to search for the record in REDCap, further explained below.
5. Log into Redcap and go to the self-report scales project (most projects use **Common Self-report Scales #collection**)
6. Click View/Edit record 
    - Under the Data Search box, search for scale session by SCALEID or REDCapID
7. Fill out Scales Admin Page, mark form as complete (you can move through the instruments in REDCap by selecting “Save and Go to Next Form”
8. The Scales Survey Admin page is for if you want to skip certain scales (e.g., for time constraints), mark complete
    - Listed below are the scales administered for each timepoint, as of 4/20/2021 there is no pipeline for EF T2/T3 so you will have to manually de-select indicated scales (in red) under “Scales Survey Admin” on the left hand side and save
<img src="/executivefunction/assets/images/EF28.png" alt="scales">

### FOLDER PREPARATION
Prepare the following paper copy printouts before the MRI Visit, all of the following documents can be found on Saturn (Saturn/Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/subjectfolder)
- Admin Folder: C2 Form, W9 Form, Clincard, CNB Notes Sheet (LiBI/Executive)
- MRI Folder: MRI Screener, MRI Session Record

## MRI Visit
### EF CONSENTS
1. As of Jan, 2021 all consents have been made virtual. Navigate to [https://axis.med.upenn.edu/](https://axis.med.upenn.edu/) and select “EF [829744] Consents #consents” Project (may be updated naming due to updates/modifications to consent form)
2. Select “Add/Edit Records” from the left side and then select green “Add New Record”  
<img src="/executivefunction/assets/images/EF29.png" alt="Redcap">

3. Next, select “Admin” and fill out all necessary fields. Mark “Form Status” as “Complete” and hit save and go to next form. This will automatically generate the correct forms based on the indicated DOB of participant.
<img src="/executivefunction/assets/images/EF30.png" alt="Redcap Admin">

4. To open, select the form on the left side panel and same as above, on Scales Instructions, select “Open Survey” on the top left of the screen.
<img src="/executivefunction/assets/images/EF31.png" alt="Survey instructions">

5. After completing the consents, there will be a green circle on the left indicating it was completed. IMPORTANT: after completion, always download the forms following these steps:
- Click to the “Admin” page on the left-side, click “Download PDF of instrument” then select “All Forms/Surveys with saved data (compact)” then save this PDF to the folder on Saturn (afp://Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/VIRTUAL EF ASSESSMENTS/CONSENTS/)
<img src="/executivefunction/assets/images/EF32.png" alt="Save consent">

**REMINDER: THIS IS PHI SO REMEMBER TO DELETE THE PDF FROM YOUR DOWNLOADS FOLDER**

### PRELIMINARY SCAN-DAY PROCEDURES (to be completed right after consents)
**Demographics**: 
1. On oracle, select “Study Enroll” on the left-side panel → select “Demos Store” and enter the BBL
2. Note: If they were not already enrolled during CAPA, then select “Study Enroll” and enroll them using the date they signed the consent form, when completed you will be automatically sent to the demographics page
3. Note: There should be a demographics update at each interaction with participant (both CAPA and scan day)

**Medications**: 
1. On Oracle, select “Medication” on the left-side panel →  select “NewCollect MedStore” and enter the BBL → select “Do medication entry”. – enter the corresponding information, visit #= the timepoint you are collecting for
2. Note: Will need exact dates of start/completion of medication

**Metal Screener**: (procedure as of April, 2021—subject to change)
1. Print paper screener which can be found here: afp://Saturn/Coordinators/Protocols/TED_PROTOCOLS/EXECUTIVE_829744/subjectFolder/mri/ Generic_MRI_metal_screen_UPDATE
2. Ask parent to complete the form and sign
**NOTE: when you get down to the scanner have MRI Technologist review the form and sign at the bottom**


### COMPUTERIZED NEUROCOGNITIVE BATTERY (CNB)
_Refer to Lisa D'Errico for specific directions on administration of CNB’s (in person or remote)_
Note: for timepoint 1 you will be completing LiBI CNB on CAPA-day and only EXECTS CNB on scan-day. For T2/T3 you will complete BOTH LiBI and EXECTS 

**EF-Specific Set-Up** 
- Timepoint 1: Administer the EXECTS CNB with EXECTS site ID. Full LiBI CNB is administered on intake day under LiBI site ID. BBLID = SUBID.
- Timepoint 2/3: Administer EXECTS CNB with EXECTS site ID, and LIBI CNB with EXECTS site ID. 
- For in-person assessments, navigate to [https://webcnp.med.upenn.edu/](https://webcnp.med.upenn.edu/) then select “Administer WebCNP Battery” and you will be prompted to sign in
- For virtual assessments, refer to the guides and site-mapping specs in the Coordinators channel. The LiBI battery on T2 can be administered virtually, but the EF CNB  must always be administered in person. 
- Fill in the remaining fields as well as the following page which asks about DOB, education, sex, handedness
**Reminder: as per CNB training remember to go back to “validate session” and fill in any notes on the assessment**
<img src="/executivefunction/assets/images/EF33.png" alt="CNBs">

### VARIABILITY
1. On the EF laptop, enter the common password, go to the IIV battery folder on the desktop
2. Go to log_files and create a new folder outside “TIMEPOINT1” and “TIMEPOINT2”: BBLID for T1, BBLID_SCANID for T2
3. Attach the EF console to the computer via the wire
4. Click on the presentation file for the IIV battery, and then when it opens up, go to “Scenario”. In the sidebar, navigate to the folder you just created, and click the “<<” button to replace the previous log file being used
5. Then go back to the main menu, click “Continue”, and enter BBLID for T1, BBLID_SCANID for T2/T3
6. Then,  select the first three tasks and the last one. Hit run non-stop, click “Enter” to get past “Ready…” and then “X” out, click finish, and “save experiment”
7. Log into PennBox (or the Box with your PennKey), and move the log_file into timepoint1/2 under the Variability tasks. Also move the log file into the correct folder on the EF laptop, i.e: TIMEPOINT1 or TIMEPOINT2
8. Troubleshooting: [in case of error]
    - Disconnect and reconnect the variability apparatus and start again
    - Make sure the log file is not within the “TIMEPOINT 1” or “TIMEPOINT 2” folders

### SELF-REPORT QUESTIONNAIRE ADMINISTRATION
1. Note: Both child and parent will be completing self report questionnaires. The proband scales are 3 surveys, the child will be more depending on the timepoint how many
2. Navigate to RedCap at the link [here](https://axis.med.upenn.edu/), sign in with your RedCap credentials and select project titled: “Common Self Report Scales #collection”
3. Click “Add/Edit Records” on the left side panel and enter the BBL ID and select the scales with the Redcap ID that you generated through oracle 
4. Fill out the Scales Admin page and click save and go to next form. On Scales Instructions, select “logout + Open Survey” on the top left of the screen (screenshot below) and you will review instructions verbatim with participants. (see additional notes on how to administer below)
<img src="/executivefunction/assets/images/EF34.png" alt="Scales instructions">

5. If participants don’t have any questions, you can click “submit” and the participant will move through the self-report scales, survey to survey until they are finished. Then they will get the below screen.
<img src="/executivefunction/assets/images/EF35.png" alt="STOP">

6. You will then need to enter a validation code. Please also enter any notes fields you see fit. If you select any validation code other than “valid”, you must include notes as to what led to your selection.
<img src="/executivefunction/assets/images/EF36.png" alt="Validation">

7. If you click past this (or the participant does) you are able to enter the validation code “offline” as well by going into the record at a later time and clicking into the form “Scales Validation”.
<img src="/executivefunction/assets/images/EF37.png" alt="Validation post survey">

*Miscellaneous but important notes:* 
- During instructions page, please reiterate to the participant that they should try to answer each question and take their best guess if they’re unsure, and that they are able to skip any questions they do not feel comfortable answering. 
- Don’t forget to give collateral the 3 short questionnaires to fill out about the proband, preferably during a time when they are not with the proband
- Remind participant to ask the coordinator if they have any questions about any of the questionnaires or items.
- For participants under the age of 18, we stay in the room so we’re close by for questions. For very young children (e.g., younger than 10) you will likely want to proctor the scales administration (i.e., read each question aloud - specify that in the notes section). For older participants (i.e., 18 and older) it’s OK to tell the participant you’ll wait outside and are nearby if they have questions.
- You should make a REDCap report so you can follow along when the forms are marked as complete (please reach out to the CRM so they can show you how to create this if one is not already created). This is to ensure 1) they are moving along and not stuck 2) that they are attentively answering questions and not distracted3) they’re not just clicking the same answer over and over just to get it done. 

### PRE-SCAN ITEMS
1. **Practice task: [duration = 3-5 min.]:**
 - Using the EF small black HP laptop, go through the practice N-Back task that they will encounter during the scan
   Note: This must be completed prior to the scan
- EF Black PC Laptop → enter common password → click on EFR01 (the presentation) on the desktop → Click run scenario or run non-stop
- You will see a page that says “Ready” – Press enter to continue
- The instructions for the 0-Back will appear → read the instructions below, press the Space Bar to continue to 2-back → After you have completed giving the instructions press “ESC” → “Continue” → “Run non-stop” to begin the task

*Instructions: “This is the n-back fractal task that you will play during the scan. In the scanner, you will have a screen that shows the task and a remote that you will hold in your dominant hand throughout the scan. In the actual scan, you will press the left blue button to respond, for right now, we will practice with you pressing the ‘B’ button on the computer keyboard. The test has two parts, we’ll practice both parts. The first part is the 0-back. Press the “B” button as fast as you can whenever you see this purple picture (point to picture). Do you have any questions about the 0-back? Great! The second part is the 2-back, press the “B” button as fast as you can whenever the picture you see is the same as the one that came two before, or two-back. You can see in this example, there is the fire picture, stripped picture, then the fire picture again. You’d press the button when you see the last fire picture because it’s the same as the one that came two before or two back (pointing throughout). Any questions before we begin the practice? Great!”*
*Observe practice to ensure they understand. Repeat if they do not seem to understand.* 

2. **Radiology Check-In: [duration = 10-20 min.]**
- 20-30 minutes before the scheduled scan time escort participant and collateral to radiology for them to be checked in (good time for participant to use the bathroom at radiology)
*Note: Parent/legal guardian is needed to sign necessary consent information at Radiology*

3. **Pre-Scan Self Reports: [duration = 5 min.]**
- On RedCAP, the second set of self-reports generated from oracle will have 2 short surveys to be completed either at HUP6 or right before you go down to radiology (see notes above on axis self-report generation and administration)

*Instructions: The first survey is about how you feel right now, in this moment, about to get in the scanner. Fill in the bubbles and press submit when you are finished. This will take you to a second survey. When finished, hit submit and tell me you’re done.*

### SCAN
