Identity Governance & Administration (IGA)
This project focuses on Identity Governance and Administration (IGA) using Microsoft Entra ID, demonstrating how to manage the employee identity lifecycle, including onboarding new employees, updating access permissions as they move between teams, and revoking access when they leave the organization.

Part 1: Designing the Automated JML Lifecycle Workflow


The Joiner (Onboarding): Provision new hires and contractors securely, grant appropriate role-based access, and enforce security policies from the outset without manual IT tickets.

•	Trigger Source: HR inputs the new employee’s basic details, employment type (employee vs. contractor), department, manager, and confirmed start date into Workday.

•	Action Taken: The Identity Provider provisions the employee's official identity, adds the employee to groups based on their roles, and enforces baseline security 

•	System of Record: Workday 



2. The Mover (Internal Transfer)
•	Trigger Source: HR updates the employee's department or role in Workday.

•	Action Taken: Identity provider re-evaluates the employee's permissions to fit the new role, eliminating permission creep as the employee transitions into the new role.

•	System of Record: Workday 


Part2: Access Certification & Audit Campaign


User Account	Role / Department	Last Login Activity	Active Entitlements / Groups	Compliance Violation / Risk Identified	Action Required (Certify / Modify / Revoke) & Justification
j.doe@omnicorp.com	Marketing Manager	2 days ago	Marketing-All, Jira-Users, Prod-Database-Admin	Multiple role-based access identified.
Marketing manager shouldn’t be a Prod Database admin	Modify access to reflect employees current position.
c.smith@contractor.io	External Developer	145 days ago	GitHub-Core, AWS-Dev-Access		Revoke. All active sessions should be killed
a.jones@omnicorp.com	Former SysAdmin (Terminated)	180 days ago	Global-Tenant-Admin, Domain-Controllers	Possibly a disgruntled employee who could be an insider threat. Possible data exfiltration	Revoke. All active sessions should be killed.
Audit should be performed to ascertain former employees activity in the past 180 days.
m.chen@omnicorp.com	Transfer: Sales  Finance	Today	Sales-CRM-Full, Finance-Billing-System	Multiple Role-based access identified. Employees former department permission should be removed to reflect their new role	Modify





4. The Leaver (Offboarding)
•	Trigger Source: HR logs an effective termination date, contract expiration date, or immediate termination status in Workday.

•	Action Taken: An automated offboarding workflow executes an instant kill-switch. The user account status in the IdP is moved from "Active" to "Disabled/Blocked." All open sessions and logins are revoked across all platforms

•	System of Record: Workday 
