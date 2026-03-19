# Permission Analysis — Master Data: Users

## 📌 Development Criteria (from my boss)
- Director can assign system permissions to employees.  
- Employees should only access limited parts of the system based on their actual work.  
- Company hierarchy has three fixed roles: **Director, Manager, Staff**.  
- IT team creates initial employee accounts, sets basic info, and sends login details via email.

## ⚠️ Challenge
- Pure Role-Based Access Control (RBAC) with only 3 fixed roles is too rigid.  
- Employees in the same role would have broad access, conflicting with the requirement for department/individual restrictions.  
- Need a more flexible model.

## 🔧 Analysis
- Sales staff should only access sales pages; production staff should only access production pages.  
- Attribute-Based Access Control (ABAC) or group-based permissions are more suitable.  
- Permissions should be designed at **group level** and extendable to **individual employees**.  
- When new modules (e.g., Sales, Production) are added, the system should automatically create default permission groups for those departments.  
- This reduces manual work for the Director and ensures consistent permission structures.

### Comparison
- **RBAC (Role-Based Access Control):** Works well in systems with many defined roles. For example, Microsoft Azure RBAC defines multiple roles with associated permissions once created.  
  - Reference: [Azure Role-Based Access Control (RBAC) Overview](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview)  
- **ABAC (Attribute-Based Access Control):** More flexible, allows permissions based on attributes such as department, group, or individual.  
- For this project, ABAC/group-based design is more appropriate.

## 🛠️ Code Review Example
- **Viewing Profile (EmployeeDetailView):**  
  - Users can always view their own profile.  
  - To view others: must be in Director group OR have `accounts.view_userprofile` permission.

- **Editing Profile (EmployeeUpdateView):**  
  - Users can always edit their own profile.  
  - To edit others: must be in Director group OR have `accounts.change_userprofile` permission.

## 📊 Outcome
- Permission design shifted from fixed-role RBAC to flexible group/attribute-based control.  
- Ensures Director retains authority but avoids overexposure of system functions to staff.  
- Supports scalability when new modules are introduced.

## 🎯 Lessons Learned
- Fixed roles alone are insufficient for complex organizational structures.  
- Attribute-based or group-based permissions provide necessary flexibility.  
- Default group creation for new modules reduces administrative overhead.  
- Protecting manager/Director content is critical to avoid accidental overwrites.

## 📌 Next Steps
- Implement group-based permission model.  
- Test with Sales and Production modules.  
- Document Director workflows for assigning permissions.  
- Align IT onboarding process with new permission structure.
