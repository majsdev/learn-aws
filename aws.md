# AWS
- [S3](#s3)
- [IAM](#iam)

# S3 
Simiple storage service, **Object**-based storage
- S3 replicates data across at least *3* AZ (availability zone)s to ensure 99.99%
availability.
- objects can be size from 0 *bytes* up to 5 terabytes
- access control is configured using *bucket policies* and *access control
  list* (ACL), which is a legacy method (not deprecated)

# IAM
Identity access management
## What is it?
A management system of *users* and *resources*

## Core components
- [IAM Policies](#iam-policies)
- [IAM Identities](#iam-identities)


### IAM Policies
JSON documents *attached to IAM identities* to grant premission for accessing services
- managed policies: managed by AWS, cannot be edited (labeled with organe box)
- customer managed policies: created by customers (reusable)
- line line policis: directly attached to the user (one-off, not reusable)

![Sample IAM Policy](./images/sample-iam-policy.png)

### IAM Identities
- IAM Users
- IAM Group
- IAM Roles

#### IAM Users
  End users who log into the console or interact with AWS resource programmatically

#### IAM Groups
  Group of IAM users that share permissions (admin, dev, auditors)

#### IAM Roles
  Associate permissions to a role and then assign this to users or groups or AWS resources. 
  e.g. 

  Can have multiple policies
  
  Q: Why have roles when you can attach (inline) policies to users and groups?
  
  A: See them as hats that you can put onto users/groups. e.g. Admin role with all permissions, guest role with read only permission, and etc.


