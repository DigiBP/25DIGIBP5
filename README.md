# Digitalisation of the Onboarding Process

## Introduction

- Punkt 1
- Punkt 2
- Punkt 3

## Team Members

- Jasmin Winter
- Gilles Müller
- Claudio Schwaiger

# As-Is Process
The onboarding process begins in the HR department, when HR receives the signed contract of the new employee. After creating a new employee profile in Enboarder, an automatic e-mail is sent to the supervisor, requesting them to complete the PDF form “Request New Employee”. HR further creates an Active Directory User for the new employee.

After HR receives the completed form from the supervisor by e-mail, they add the new entry in Confluence and open a ticket in the internal ticketing system “ServiceNow” with the PDF attached to initiate the process of setting up the new employee’s equipment by the IT department.

Communication between the HR and IT department is centres around ServiceNow and the Confluence page to provide information on the ticket status of the new employees entries. The Confluence page is maintained by IT department as a comprehensive overview for HR, as the status of the ticket can only be queried on a user-specific basis in ServiceNow.

To ensure hardware provision to the new employee on time, the ticket must be created at least two weeks prior to the employee’s start date. When the IT department receives the ticket, it checks it for completeness and accepts the new ticket. If the ticket does not meet the time criteria, the availability of the hardware on the start date cannot be guaranteed and a new date must be set for the hardware handover.

The PDF “Request New Employee” is then saved in the network drive and the Confluence page is updated. Furthermore, the IT department opens a ticket at the external provider’s ticketing system, requesting the setup of the hardware of the new employee. The external ticketing system is the primary communication channel with the external provider. The requested setup includes configuring the notebook, ordering a proxy, granting user access and creating the user in the MDM system. These tasks at the IT department generally require two working days.

There is an SLA with the external provider in place. The ticket must be processed and finalised within six working days, including handover of the hardware back to the IT department.
Upon receiving the notebook, the IT department verifies the completeness and, if necessary, finalises the setup. The notebook is then personalised and access to the required file shares configured. Further the business mobile is prepared. One to two working days before the employees start date, the workstation is completely setup to ensure everything is ready on the first day. The last step is to update the Confluence page.

The supervisor is informed by HR about the readiness of the hardware by e-mail.

On the first workday, the new employee receives their hardware from the IT department and takes part in an introductory IT training session.

HR also notifies the SAP department about the new employee for user creation. The SAP then carries out a user comparison in the system and creates the new user account. If no additional rights are required, the account is handed over to the new employee.

If additional rights are required, the supervisor opens a ticket in ServiceNow to request the necessary roles. An authorization request is created at SAP department and the signature of the key user is obtained. The supervisor signs the request, and the account is updated accordingly.

## Challenges

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


## DMN


## Forms


```bash
git clone https://github.com/dein-benutzername/dein-repo.git
cd dein-repo


---

### 🔧 Erklärung der wichtigsten Markdown-Elemente

| Element        | Syntax                     | Beispiel                                  |
|----------------|----------------------------|-------------------------------------------|
| **Überschrift** | `#`, `##`, `###`, ...      | `## Mein Titel` → Untertitel              |
| **Fett**        | `**Text**` oder `__Text__` | `**wichtig**` → **wichtig**               |
| **Kursiv**      | `*Text*` oder `_Text_`     | `*betont*` → *betont*                     |
| **Liste**       | `-` oder `*`               | `- Punkt` → Aufzählung                    |
| **Code (inline)** | `` `code` ``              | `Der Befehl ist `git status``             |
| **Codeblock**   | ``` dreifache Backticks ```| Siehe Installation-Beispiel oben          |
| **Link**        | `[Text](URL)`              | `[GitHub](https://github.com)`            |
| **Bild**        | `![Alt](URL)`              | `![Logo](logo.png)`                       |

---

Wenn du magst, kann ich dir gleich ein README-Grundgerüst für dein Projekt erstellen – sag mir einfach, worum’s geht (z. B. Projektthema, Ziel, Features).
