Identity Governance & Administration (IGA)
This project focuses on Identity Governance and Administration (IGA) using Microsoft Entra ID, demonstrating how to manage the employee identity lifecycle, including onboarding new employees, updating access permissions as they move between teams, and revoking access when they leave the organization.


The Joiner (Onboarding): Provision new hires and contractors securely, grant appropriate role-based access, and enforce security policies from the outset without manual IT tickets.

•	Trigger Source: HR inputs the new employee’s basic details, employment type (employee vs. contractor), department, manager, and confirmed start date into Workday.

•	Action Taken: The Identity Provider provisions the employee's official identity, adds the employee to groups based on their roles, and enforces baseline security 

•	System of Record: Workday 



2. The Mover (Internal Transfer)
•	Trigger Source: HR updates the employee's department or role in Workday.

•	Action Taken: Identity provider re-evaluates the employee's permissions to fit the new role, eliminating permission creep as the employee transitions into the new role.

•	System of Record: Workday 



4. The Leaver (Offboarding)
•	Trigger Source: HR logs an effective termination date, contract expiration date, or immediate termination status in Workday.

•	Action Taken: An automated offboarding workflow executes an instant kill-switch. The user account status in the IdP is moved from "Active" to "Disabled/Blocked." All open sessions and logins are revoked across all platforms

•	System of Record: Workday 
