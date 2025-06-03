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
# Process Improvements
## Benefits of the New Onboarding Process
The improved onboarding workflow delivers tangible benefits across teams:

### Higher Automation
- Key steps like contract handling, ticket creation, setup payload generation, and SAP account provisioning are now automated.
- Result: fewer manual handovers, reduced error rates, and faster turnaround times.
 
### Unified Platform
- All teams work within the same centralized ticketing system (e.g. ServiceNow).
- This creates a **single source of truth**, ensuring consistent data and better traceability.
 
### Improved Handling of Short-Notice Hires
- Automatic notifications for hires with <2 weeks’ lead time.
- Replaces fragile workarounds (e.g. saving forms to file shares) and improves preparedness.
 
### Clear Role Allocation
- Responsibilities are defined:
 - **HR** → Contract management 
 - **IT** → Hardware preparation 
 - **SAP Team** → Account creation
- Leads to smoother collaboration and fewer misunderstandings.
 
### Measurable Process Completion
- Process concludes with a defined step: _“Onboarding new employee completed”_.
- Enables structured reporting and quality monitoring.
 
### Scalability Through Structured Workflows
- The standardized and automated setup scales efficiently across teams and sites.
- Ideal for growing organizations or high onboarding volumes.

# PROCESS START - AUTOMATED CONTRACT CREATION AND DELIVERY

## BPMN Overview

This part of the digital onboarding process starts with the event **`New contract requested`**, which is triggered by HR when a new employee is to be onboarded. It then handles the automated generation, dispatch, and tracking of employment contracts. It ensures that contract data is captured in a structured format, transmitted to external services for processing, and monitored until the signed document is returned. All steps are fully automated and require no manual intervention after HR submits the initial form.

## WHAT THIS MODULE DOES

### GOAL
To automate the contract creation and delivery process by digitizing employee data input, generating PDF contracts, logging relevant data, and waiting for confirmation — all while maintaining process stability and compliance.

### FLOW SUMMARY
- HR fills out a structured input form in Camunda  
- All form fields are mandatory to ensure completeness and data quality, and to enable fully automated downstream processing without the need for manual data correction  
- A script task generates a JSON payload (`contractPayload`) from the form data  
- A service task sends the payload to a Make.com scenario  
- Make.com creates a PDF contract (via PDF.co) and logs the data in Google Sheets  
- The payload is removed after dispatch to prevent serialization issues, specifically Spin deserialization errors such as `SPIN/JACKSON-JSON-01006`, which may occur if nested objects persist across asynchronous steps  
- Camunda waits for the signed contract (up to 7 days) using an event-based gateway. If the message is not received within this period, a timer boundary event on the message catch task ends the process  
- If received: process continues  
- If not received: process ends

## IMPLEMENTATION DETAILS

### CAMUNDA BPM
- **User Task:** `Define contract` — HR enters all relevant data via structured form  
- **Script Task:** `Create contract` — transforms data into `contractPayload` (JSON)  
- **Service Task:** `Send contract` — sends payload to Make via HTTP  
- **Script Task:** `Remove variable` — deletes `contractPayload` to prevent Spin deserialization errors  
- **Message Catch Event:** waits for `SignedContractReceived`  
- **Timer Boundary Event:** cancels the process if no signature is returned within 7 days

![image](https://github.com/user-attachments/assets/cb974c86-4400-4f59-b56f-5cb3561b951d)

### MAKE SCENARIO OVERVIEW
- **Webhook** receives the payload from Camunda  
- **Router** triggers two parallel paths:  
  - **PDF.co:** generates the contract as PDF  
  - **Google Sheets:** creates a new row entry that logs all relevant employee and contract information, including:  
    - Employee name and ID  
    - Start date  
    - Contract status  
    - Timestamp of creation
 
![image](https://github.com/user-attachments/assets/3e824059-3347-4e87-9215-eca8c95b09f3)
![image](https://github.com/user-attachments/assets/3f387e33-8196-4626-9548-9055afc6d937)

### FUTURE IMPROVEMENTS - eSIGNATURE INTEGRATION
The process can be extended to include digital signing via services like **DocuSign** or **Adobe Sign**. After contract generation, the PDF would be:
- Sent automatically for signature
- Tracked via API callback or polling
- Stored with legal validity
This would complete the contract flow digitally and eliminate manual handovers.

### VARIABLE CLEANUP - JAVASCRIPT
execution.removeVariable("contractPayload");
execution.removeVariable("ticketPayload");

### RELATED TOOLS
- Make (Integromat): Automation platform
- Camunda Modeler: BPMN workflow management
- Google Sheets: Central data hub for information on employee


## Jasmin plus DMN
![image](https://github.com/user-attachments/assets/fde8ac36-606a-478c-8d8b-a0e1f5227aab)

This repository contains a DMN (Decision Model and Notation) table used to determine the appropriate IT setup for new employees during the onboarding process. The decision logic ensures standardized, rule-based allocation of hardware, software, phone equipment, and encryption settings based on employee role and mobility requirements.
### SAP Ticket 
![image](https://github.com/user-attachments/assets/5eee5d17-5ccd-45e5-8426-259cee65e470)


 ![image](https://github.com/user-attachments/assets/a0afef93-67ac-4bbc-9aed-4a6fcd081fa9)

### Purpose
 
The DMN decision table automates the selection of IT equipment and software configurations for new hires. It supports consistent decision-making and reduces manual coordination between HR, IT, and other stakeholders.
 
### Input Parameters
 
- `Role` (string): The employee's job function (e.g., "Office Employee", "CAD Designer", "Software Developer")
- `Mobility` (boolean): Indicates whether the employee requires a mobile setup (true/false)
 
### Output Parameters
 
Based on the combination of `Role` and `Mobility`, the following outputs are defined:
 
- `Hardware`: The assigned device type (e.g., ThinClient, Notebook, Workstation)
- `Application`: The main application package needed (e.g., M365, Team Center, Visual Studio)
- `Phone`: Type of phone equipment assigned (e.g., IP phone, iPhone 16 SE)
- `Encryption`: Whether encryption is required for the setup (true/false)
 
### Example Rules
 
| Role              | Mobility | Hardware              | Application        | Phone         | Encryption |
|-------------------|----------|------------------------|--------------------|---------------|------------|
| Office Employee    | false    | ThinClient (Igel)      | M365               | IP-Telefon     | false      |
| Office Employee    | true     | Notebook Office (T14)  | M365               | iPhone 16 SE   | true       |
| CAD Designer       | false    | Workstation CAD (P5)   | Team Center, NX    | IP-Telefon     | false      |
| CAD Designer       | true     | Notebook CAD (P15)     | Team Center, NX    | iPhone 16 SE   | true       |
| Software Developer | true     | Notebook Entwickler    | Visual Studio      | iPhone 16 SE   | true       |
| Software Developer | false    | Workstation Entwickler | Visual Studio      | IP-Telefon     | false      |
 
### Benefits
 
- Reduces manual effort in IT configuration
- Ensures consistent and secure setup across the organization
- Easy to extend and maintain as roles or equipment evolve
- Integrates into automated onboarding workflows
 

![image](https://github.com/user-attachments/assets/b9b2331c-df8b-481c-a406-519c033abc0c)


## AUTOMATED DELIVERY DATE CHECK FOR NEW EMPLOYEE ONBOARDING

![BPMN Overview](https://github.com/user-attachments/assets/e89325c7-aa8a-49dc-bb89-47378c29ab23)

This Part in the digital onboarding process ensures that IT hardware can be delivered on time for new employees. It validates if the lead time before the employee's start date is sufficient and triggers appropriate actions if not.

If the entry date is **less than 14 days away**, a new delivery date is calculated automatically, the supervisor is informed, and the onboarding ticket is updated—**all without manual interaction**.

### WHAT THIS MODULE DOES

#### GOAL

To ensure timely and realistic planning for hardware setup and delivery in the onboarding process.

#### FLOW SUMMARY

1. Camunda triggers a **Make scenario** using webhook integration.
2. Make checks whether the current delivery timeline is too short (less than 14 days).
3. If too short:
   - A new delivery date is calculated (request date + 14 days)
   - The supervisor is notified by email
   - Google Sheet entry is updated
   - Camunda is informed: `IsTooShortNotice = true`
4. If timeline is okay:
   - Process continues as planned with the existing delivery date

### IMPLEMENTATION DETAILS

#### CAMUNDA BPM

* A **Service Task** sends data (Employee ID, start date, etc.) to the webhook in Make.
* An **Exclusive Gateway** checks the response variable `IsTooShortNotice`.
* Depending on the value:
  - If true: triggers supervisor notification and updated delivery planning
  - If false: uses the initially submitted date
* The variable `deliveryDate` is used in both paths to keep the logic consistent.

#### MAKE SCENARIO OVERVIEW

![Make Scenario Router](https://github.com/user-attachments/assets/3f1f4a1f-70c5-4aed-b1bb-cd2d6cc3c6e5)

This is the automation logic inside Make:

1. **Webhook** receives the Camunda request
2. **Search Rows**: Finds the employee in Google Sheets using Employee ID
3. **Filter / Condition**: Checks if entry date is at least 14 days away
4. **If too short notice:**
   - New delivery date is calculated (request date + 14 days)
   - Sheet is updated with:
     - New delivery date
     - Status: `"Updated"`
   - Response: `IsTooShortNotice = true`
5. **If lead time is sufficient:**
   - No change made
   - Response: `IsTooShortNotice = false`

#### DATE EVALUATION LOGIC

```js
parseDate(2.`Start Date`, "DD.MM.YYYY") < addDays(parseDate(2.`Date requested`, "DD.MM.YYYY"), 14)
```

This filter checks if the start date is less than 14 days after the request date.

### GOOGLE SHEETS UPDATE

- The corresponding row is identified using the **Employee ID**.
- The **Delivery Date** is automatically adjusted.
- The **Ticket Status** is changed to `"Updated"`.

### EMAIL TO SUPERVISOR

![Supervisor Email Notification](https://github.com/user-attachments/assets/426d24a1-5d17-430f-b2c9-9c0d5fbb5239)

If the requested delivery time is too short, the system notifies the supervisor via email. This ensures transparency and allows proactive planning.

### EMAIL TO IT PROVIDER

![IT Provider Notification](https://github.com/user-attachments/assets/165b0f83-41f1-4e10-afcd-28f99c7de6fd)

The IT provider receives a structured email with the exact hardware and setup requirements for the new employee—generated from the previously selected configuration via DMN logic.

### Hardware received and installed
After the Hardware is received from the External IT Provider the Internal IT will install the Hardware and fullfill the Usertask in Camunda the Google Forms then will update the Status of the Ticket to done with the Date and time.

### ADVANTAGES

- Fully **automated validation** of onboarding timelines
- Ensures no manual checking or chasing is needed
- Allows **supervisors to act only when necessary**
- Seamless integration between Camunda, Make, and Google Sheets
- Saves time and improves onboarding reliability

### RELATED TOOLS

- **Make (Integromat)** – Automation platform
- **Camunda Modeler** – BPMN workflow management
- **Google Sheets** – Central data hub for onboarding tickets


## ONBOARDING FIRST DAY OF THE EMPLOYEE

![image](https://github.com/user-attachments/assets/5e794a42-e610-460f-b58a-4cdd243f0f99)

As the final step of the onboarding process, a digital checklist is provided to the Supervisor to support through the Onbording Prozess so nothing is missing to ensure that all necessary steps and setups have been completed.

![image](https://github.com/user-attachments/assets/a5c2471d-1061-419d-9f7f-bea878db8dd7)

### WHAT HAPPENS

The onboarding checklist for supervisors provides a clear structure to ensure that all essential steps in welcoming and integrating a new employee are covered. It focuses not only on logistical aspects but also on culture, communication, and development from day one.

First, supervisors are encouraged to introduce the team's core values and principles. This includes explaining expected behaviors and fostering a culture of openness, trust, and ownership. 
Following that, they are responsible for organizing first-day logistics, such as meeting the new employee at reception, handing over equipment if available, and confirming participation in any planned welcome events like lunch.
Next, the supervisor verifies that the IT setup is complete and that the employee has access to critical systems such as Outlook, Teams, SharePoint, and the company intranet, as well as IT support channels.
After the technical basics are in place, the organizational structure should be explained, and the new team member introduced to key colleagues and stakeholders.
An initial development session should also be scheduled to talk about available training options, career development tools, and performance expectations.
Finally, the checklist includes completing administrative onboarding tasks—supporting data entry in the HR system and ensuring that access badges and necessary permissions are issued.
Overall, the checklist helps supervisors deliver a structured, smooth, and professional onboarding experience that supports both immediate productivity and long-term engagement.

This ensures formal closure of the onboarding process and provides traceability.

### BENEFITS

- Standardized onboarding experience for all employees.
- Digital confirmation ensures transparency and accountability.






