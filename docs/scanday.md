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
