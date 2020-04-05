# AWS
- [S3](#s3)
- [IAM](#iam)
- [Cognito](#cognito)

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

### IAM Access Keys
Allow users to interact with AWS service programmatically via CLI or SDK
Two access keys per user

### IAM MFA
Multi-factor authentication can be turned on per user.
The user has to turn on MFA themselfs (because administrators have no access to users' physical deviced, but they can create policy to require MFA)

# Cognito
## What is it?
Decentralized managed authentication

- [Cognito user pools](#cognito-user-pools)
- [Cognito identity pools](#cognito-identity-pools)
- [Cognito sync](#cognito-sync)

Web Idenity Federation: to exchange identity and security information
between an identity provider (IdP) and an application

Identity provider (IdP): a truster provider of your user identity that lets
you use authentication to access other service
Example identity providers: fb, amazon, google, twitter

Types of IdP: OpenID connect (OIDC), SAML (for single sign on)

### Cognito user pools
user pools are user directories used to managed the action for web and
mobile apps such as:
- sign up
- sign in
- account recovery
- account confirmation
