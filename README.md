The Smart Vehicle Service & Maintenance CRM is a Salesforce-based CRM solution designed to optimize vehicle servicing operations. It connects Customers, Technicians, and Service Managers into one system to streamline service request handling, workload management, parts tracking, invoicing, and customer communication.

This project demonstrates the use of Custom Objects, Page Layouts, Profiles, Sharing Rules, Lightning Web Components (LWC), and Automation in Salesforce.
Use Cases
1. Service Request Management:
->Customer books a service request (via form/portal).
->System auto-assigns a technician based on skills & workload.
->Customer receives confirmation via email/SMS.

2. Vehicle History Tracking:
->Every service request is linked to the customer’s vehicle.
->System auto-updates Last Service Date.
->Service history visible to technicians & managers.

3. Technician & Workload Management:
->Service Manager assigns/auto-assigns jobs.
->Technicians view assigned tasks on their LWC dashboard.
->Status updates: In Progress → Completed.

4. Parts & Inventory Management:
->Parts used during service are logged automatically.
->Inventory stock auto-reduces.
->Low stock alerts triggered if threshold is reached.

5. Preventive Maintenance Reminders:
->Monthly batch job sends preventive service reminders.
->Notifications via email/SMS.

6. Invoice & Payment Handling:
->Auto-generated invoice on service completion.
->Invoices > ₹10,000 require approval.
->Online payment supported via payment gateway integration.

7. Customer Communication:
->SMS/Email notifications at each stage: Booked, In Progress, Completed.
->Customers can track service status on portal (LWC).

8. Reporting & Dashboards:
->Service requests by type (regular, emergency, annual checkup).
->Technician productivity & workload distribution.
->Monthly revenue per service center.
->Inventory usage & trends.

This project was implemented from scratch in Salesforce with the following 


1.Custom Objects Created:
  Vehicle__c → Stores customer vehicle details.
  Service_Request__c → Tracks service bookings and status.
  Technician__c → Holds technician details.
  Parts_Inventory__c → Manages spare parts & stock.
  Service_Parts_Used__c → Logs parts consumed during service.
  Invoice__c → Handles billing and payments.


2.Page Layouts & Fields Configured:
  Custom fields (Date, Lookup, Picklist, Currency, etc.) created for each object.
  Page layouts customized for Technician, Service Request, Vehicle, Parts Inventory, Invoice.


3.Profiles Created:
  Service Manager Profile → Read/Write on all service-related objects.
  Technician Profile → Read/Write only on assigned requests, update status & parts used.
  Customer Service Agent (CSA) Profile → Can create service requests, view status, and manage customer communication.


4.Roles Created:
  Service Manager
  Technician (reports to Service Manager)
  Customer Service Agent (reports to Service Manager)


5.Users Configured:
  Service Manager → Role: Service Manager | Profile: Service Manager Profile
  Technician → Role: Technician | Profile: Technician Profile
  Customer Service Agent (CSA) → Role: Customer Service Agent | Profile: CSA Profile (cloned under Platform User license)


6.Sharing Rules & Security:
  Org-Wide Defaults (OWD):
  Vehicle, Service Request, Invoice → Private
  Parts Inventory → Public Read Only
  Sharing Rule: Service Manager-owned Service Requests → Shared with Technicians (Read/Write)


7.Metadata Retrieved & Source Control:
  Retrieved objects, profiles, layouts, and sharing rules into VS Code using Salesforce CLI.
  Cleaned metadata to keep only relevant project components.
  Integrated with GitHub for version control and submission.
