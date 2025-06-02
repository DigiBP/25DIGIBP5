# Digitalisation of the Onboarding Process

# Team Members

- Jasmin Winter
- Gilles Müller
- Claudio Schwaiger

## Introduction

The company, headquartered in Zurich, Switzerland, is a subsidiary of a German industrial group and a recognized leader in the development of advanced air defence systems. With approximately 1,000 employees, the company specializes in radar-guided target tracking systems, anti-aircraft artillery, and missile defence technologies. Its globally deployed solutions—such as modular defence platforms—are known for their accuracy and high operational effectiveness.

The organization benefits from a centralized and standardized IT strategy defined at group level.

This project aims to address inefficiencies in the current onboarding process by focusing on the **digitalization of cross-departmental workflows**. The existing process involves multiple internal and external systems (e.g. Enboarder, ServiceNow, Confluence, Active Directory, MDM, SAP) and stakeholders (HR, IT, SAP, supervisors, external providers). Despite having a defined structure, the process is heavily dependent on manual activities and informal communication channels.

### Goal
The core objective of this digitalization initiative is to ensure that new employees are equipped with all necessary IT hardware and system access on their first working day. This requires a fundamental redesign of the existing onboarding process, which is currently characterized by high manual effort, fragmented systems, and inconsistent handovers.

Key goals include:
- **Digitalizing the end-to-end onboarding process** to eliminate manual dependencies,
- **Reducing process delays** between stakeholders by streamlining and standardizing communication, and
- **Automating repetitive and time-sensitive activities**, such as ticket creation and form handling.

These improvements aim to increase operational efficiency, reduce onboarding lead time, and ensure a positive employee experience from day one.

# As-Is Process

The onboarding process begins in the HR department, when HR receives the signed contract of the new employee. After creating a new employee profile in Enboarder, an automatic e-mail is sent to the supervisor, requesting them to complete the PDF form “Request New Employee”. HR further creates an Active Directory User for the new employee.

After HR receives the completed form from the supervisor by e-mail, they add the new entry in Confluence and open a ticket in the internal ticketing system “ServiceNow” with the PDF attached to initiate the process of setting up the new employee’s equipment by the IT department.

Communication between the HR and IT department is centered around ServiceNow and the Confluence page to provide information on the ticket status of the new employee’s entries. The Confluence page is maintained by IT as a comprehensive overview for HR, as the status of the ticket can only be queried on a user-specific basis in ServiceNow.

To ensure hardware provision to the new employee on time, the ticket must be created at least two weeks prior to the employee’s start date. When the IT department receives the ticket, it checks it for completeness and accepts the new ticket. If the ticket does not meet the time criteria, the availability of the hardware on the start date cannot be guaranteed and a new date must be set for the hardware handover.

The PDF “Request New Employee” is then saved in the network drive and the Confluence page is updated. Furthermore, the IT department opens a ticket at the external provider’s ticketing system, requesting the setup of the hardware of the new employee. The external ticketing system is the primary communication channel with the external provider. The requested setup includes configuring the notebook, ordering a proxy, granting user access and creating the user in the MDM system. These tasks at the IT department generally require two working days.

There is an SLA with the external provider in place. The ticket must be processed and finalized within six working days, including handover of the hardware back to the IT department.  
Upon receiving the notebook, the IT department verifies the completeness and, if necessary, finalizes the setup. The notebook is then personalized and access to the required file shares configured. Further, the business mobile is prepared. One to two working days before the employee’s start date, the workstation is completely set up to ensure everything is ready on the first day. The last step is to update the Confluence page.

The supervisor is informed by HR about the readiness of the hardware by e-mail.

On the first workday, the new employee receives their hardware from the IT department and takes part in an introductory IT training session.

HR also notifies the SAP department about the new employee for user creation. The SAP team then carries out a user comparison in the system and creates the new user account. If no additional rights are required, the account is handed over to the new employee.

If additional rights are required, the supervisor opens a ticket in ServiceNow to request the necessary roles. An authorization request is created by the SAP department, the signature of the key user is obtained, and the supervisor signs the request. The account is updated accordingly.

## Identified Challenges of the As-is Process

The current onboarding process faces several critical challenges that impact efficiency, transparency, and user experience. Below are the key pain points:

### High Process Complexity & Fragmentation
The onboarding workflow spans multiple systems (Enboarder, ServiceNow, Confluence, external provider systems, Active Directory, MDM, SAP) and various stakeholders (HR, IT, supervisors, SAP department, external providers).  
**Risk:** Increased coordination effort, handover delays, and risk of process breakdowns.

### Manual and Email-Dependent Communication
Key process steps—such as submitting forms, notifying stakeholders, and updating statuses—are handled manually via email.  
**Risk:** Low transparency, high error probability, and lack of auditability.

### Lack of Workflow Automation
Tasks like PDF processing, ticket creation, Confluence page updates, and internal approvals are executed without automation.  
**Risk:** Operational inefficiencies, inconsistent data, and increased manual workload.

### Time Sensitivity vs. Lack of Enforcement
Although tickets must be created at least two weeks before the start date, there are no automated controls or escalation paths to enforce this timeline.  
**Risk:** Missed hardware provisioning deadlines and onboarding delays.

### Redundant Documentation & Storage
Employee-related information is captured and stored redundantly (e.g. PDF form, network drive, Confluence, ticketing systems), often manually.  
**Risk:** Data inconsistencies, version control issues, and unnecessary duplication of effort.

### Limited Transparency & Status Tracking
ServiceNow does not offer a consolidated view of onboarding tickets. HR relies solely on a manually maintained Confluence page by IT.  
**Risk:** Poor visibility, dependency on IT updates, and inefficient coordination.

### Reactive Issue Handling
Late or incomplete ticket submissions trigger reactive measures like rescheduling hardware handovers rather than proactive interventions.  
**Risk:** Deteriorated first-day experience for new hires and reduced onboarding quality.

# To-Be Process
- explain general process flow
- no need to get into each and every task
# Digitalisation of the Onboarding Process
![image](https://github.com/user-attachments/assets/ccd98821-ccf2-46ad-b1e7-4716d8f7bf4a)
## Process Improvements Gilles
- explain what you improved
- refer to tasks (maybe)

## Jasmin
![image](https://github.com/user-attachments/assets/ea39f011-24ff-4586-a7ac-5427fb531059)


### Forms
- include picture
- why decide on setup
- explain what happens

## Jasmin plus DMN
![image](https://github.com/user-attachments/assets/fde8ac36-606a-478c-8d8b-a0e1f5227aab)
- include picture
- why decide on this setup
- explain what happns
![image](https://github.com/user-attachments/assets/b9b2331c-df8b-481c-a406-519c033abc0c)


## AUTOMATED DELIVERY DATE CHECK FOR NEW EMPLOYEE ONBOARDING

![image](https://github.com/user-attachments/assets/e89325c7-aa8a-49dc-bb89-47378c29ab23)

In the full onboarding process, once the contract is signed, the system prepares the technical setup for the new employee. This involves generating a setup payload, creating a ticket in the service portal, and triggering the delivery of required hardware.

If the entry date is too soon (less than 14 days), it may not be feasible to deliver everything on time. This module handles that situation by:

* Calculating if the request is too short notice
* Notifying the supervisor
* Automatically adjusting the delivery date
* Updating the internal Google Sheet and Camunda workflow accordingly

### WHAT THIS MODULE DOES

#### GOAL

Ensure realistic lead times for onboarding hardware delivery and communicate changes.

#### FLOW SUMMARY

1. Camunda triggers Make with entry data (start date, ticket info, etc.)
2. Make evaluates if the requested entry date is less than 14 days away
3. If yes:

   * A new delivery date is calculated (14 days from request)
   * Supervisor is notified
   * Ticket status and delivery date are updated
   * Camunda receives IsTooShortNotice = true
4. If no:

   * Process continues with the original delivery date

### IMPLEMENTATION DETAILS

#### CAMUNDA BPM

* Service Task: "Check entry date" sends data to Make webhook
* Exclusive Gateway: Evaluates IsTooShortNotice variable
* Conditional Paths:

  * If true: Notify supervisor and adjust delivery
  * If false: Continue as planned
* Downstream Use: Both paths set a common variable deliveryDate, which is used in the ticketing step

#### MAKE SCENARIO OVERVIEW
![image](https://github.com/user-attachments/assets/3f1f4a1f-70c5-4aed-b1bb-cd2d6cc3c6e5)

1. Webhook receives POST from Camunda
2. Google Sheets (Search) finds the row by Employee ID
3. Router evaluates date difference
4. If too short notice:

   * Set variable deliveryDateCalculated = requestDate + 14 days
   * Update delivery date and ticket status
   * Return response with IsTooShortNotice = true
5. Else:

   * Return IsTooShortNotice = false and keep existing date

#### DATE EVALUATION LOGIC

```
parseDate(2.`Start Date`, "DD.MM.YYYY") < addDays(parseDate(2.`Date requested`, "DD.MM.YYYY"), 14)
```

### GOOGLE SHEETS UPDATE

* Delivery Date column is set to deliveryDateCalculated
* Ticket Status column is set to "Updated"
* Row to update is found using the rowNumber from the search module

### Send Email do Supervisor if No
![image](https://github.com/user-attachments/assets/426d24a1-5d17-430f-b2c9-9c0d5fbb5239)
### Send Email to It Provider with required Hardware
![image](https://github.com/user-attachments/assets/165b0f83-41f1-4e10-afcd-28f99c7de6fd)


### ADVANTAGES

* Automated logic replaces manual review
* Human escalation only when needed (via supervisor notification)
* Dynamic update to Google Sheets without scripting
* Easily pluggable into any BPMN process with Camunda

### RELATED TOOLS

* Make (Integromat)
* Camunda Modeler
* Google Sheets (as request/ticket database)

## Onbording first Day of the Employee
![image](https://github.com/user-attachments/assets/5e794a42-e610-460f-b58a-4cdd243f0f99)
- Checkliste bild plus erklärung
  ![image](https://github.com/user-attachments/assets/a5c2471d-1061-419d-9f7f-bea878db8dd7)








