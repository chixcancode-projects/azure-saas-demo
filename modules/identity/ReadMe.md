# SaaS Identity

Module is still a work in progress.

In this module, you will use Azure AD B2C to create a customized identity experience for a SaaS application.  You will do this by creating some [custom policies](https://docs.microsoft.com/en-us/azure/active-directory-b2c/custom-policy-overview) in Azure AD B2C.

## Getting Started

1.  Create (Azure AD B2C)[https://docs.microsoft.com/en-us/azure/active-directory-b2c/tutorial-create-tenant] tenant.
2.  Create an (App registration)[https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app] in your Azure AD Tenant(not Azure AD B2C tenant).  For this, you don't need to add a redirect uri, but you do need to create a client secret, make sure to record this secret.
4.  Create a new (Policy Secret)[https://docs.microsoft.com/en-us/azure/active-directory-b2c/policy-keys-overview#policy-key-management] named B2C_1A_AADAppSecret and set key to the client secret created in step 2.
3.  Modify the TrustFrameworkExtensions.xml and change all instances of <yourB2CTenant> to your AAD B2C tenant.  Also change clientid-for-AAD to the client id created in step 2.
4.  Now you are ready to upload the policy files into your AAD B2C tenant. Upload the files in the following order:
    - TrustFrameworkBase.xml
    - TrustFrameworkExtensions.xml
    -  SignUpOrSignInPolicy.xml
5.  After you have done that go, into AuthConfig.js and modify
