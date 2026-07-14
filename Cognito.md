Decentralized Managed Auth

Cognito User Pools:
- User Dir with auth to grant access to app

Cognito Idenity Pools
- Provide temp creds to access AWS services

Cognito Sync
- Syncs user data and preferences across all devices

Web Identity Federation and IpD

Web Identity Fed 
- exchange identity sec info between and identity provider and an application

IDP
- trusted provider of user identity that lets you use auth to access other services

Idenity Providers:
OIDC -> use OAUTH, SAML

User Pools:
- user dirs used to manage actions for web and mobile apps such as Sign-up, Sign-in, Account recovery, account confirmation

users sign-in directly to user pool or using web identity fed, usese aws cognito as idenity broker, user auth create jwt, use pools can be though as the account used to access system

Identity Pools:
- temp AWS creds to access AWS services

Cognito - Sync 
- Sync user data and preferences across devices
- push sync to push updates and sync data
- uses simple notfication services to send notis