# Access Control ACL

## RBAC

Role base access control (RBAC) is a common and intuitive way of dealing with authorizing access and other permissions. It is analogous to the roles people have at their jobs and the kind access people need for thier jobs. For example, a manger might need to access all of the employee files, but an employee may only be able to access a portion of thier own. 

RBAC can be implmented with tables of roles and capabilities. These are things people are, and things they can do. So the manger can read all employee records, and employees can only read their own, for example. This could be implemented with row with columns role and capabilities of manger - READALL and employee - READOWN.

To be classifed as an RBAC should implement the following rules: [reference](https://en.wikipedia.org/wiki/Role-based_access_control#Design)

* Role assignment
* Role authorization
* Permision authorization

Role assigment would be done by an administrator, or it could be done on sign up when a user signs up as a (for example) teacher or student on an LMS system.

Role authorization would be taken care of by the software when the user attempts to access resources. The system will ensure that a particular role belongs to a particular user.

Permission authorization would also be taken care of by software. Once the role is established for a user, the software can ensure that a user with a particulare role can access a particular resource.

The important thing to remember about RBAC is that permissions are not associated directly with users. The user should have a role, and the role give the use permission. The advantage is that general policies are eaiser to manage especially for larger organizations. Another advantage is that a single user can have more than one role, and change roles as needed. This way they can't accidentally damage a resouce that doesn't need to be touched for a given task.

