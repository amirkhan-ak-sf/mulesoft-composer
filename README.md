## MuleSoft Composer APIs

In order to get the Postman Collections, either click on the Run in Postman button or go to the Public Workspace and fork the collection.
**Public Workspace**: https://www.postman.com/mulesoft-api/workspace/mulesoft-platform-apis/documentation/16547909-9c9fe65c-8e4f-488c-8475-645243dce6d9

[![Run in Postman](https://run.pstmn.io/button.svg)](https://god.gw.postman.com/run-collection/16547909-9c9fe65c-8e4f-488c-8475-645243dce6d9?action=collection%2Ffork&collection-url=entityId%3D16547909-9c9fe65c-8e4f-488c-8475-645243dce6d9%26entityType%3Dcollection%26workspaceId%3Dabca7de1-d2bb-4be1-8d2b-8d56f87dfbab#?env%5BComposer-Environment%5D=W3sia2V5IjoidXJsIiwidmFsdWUiOiJodHRwczovL2NvbXBvc2VyLm11bGVzb2Z0LmNvbSIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJkZWZhdWx0In0seyJrZXkiOiJ1c2VybmFtZSIsInZhbHVlIjoiY29tcG9zZXItYW1pcmtoYW4tYWsiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCJ9LHsia2V5IjoicGFzc3dvcmQiLCJ2YWx1ZSI6IlRvMHRoYnJ1c2ghIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImRlZmF1bHQifSx7ImtleSI6ImFjY2Vzcy10b2tlbiIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImRlZmF1bHQifSx7ImtleSI6ImNvb2tpZXMiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJhbnkifSx7ImtleSI6Im9yZ2FuaXphdGlvbl9pZCIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSJ9LHsia2V5IjoiZmxvd19uYW1lIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCJ9LHsia2V5IjoiZmxvd19pZCIsInZhbHVlIjoiMjI4MTA1YjktYmVhZC00ZTA5LWEzYzktMmQyMDJiNDhjYWQ3IiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJ1c2VyX2lkIiwidmFsdWUiOiIyMjI1YWY0MC1kOTE4LTRlYzYtODY1OS0yZjQ0NjUwMTc0OTEiLCJlbmFibGVkIjp0cnVlfV0=)

## Disclaimer

This set of request collection is completely based upon community work and enablement. MuleSoft Composer officially has no REST API documented (yet). This is a community-driven and community-supported collection of assets for you to get started with MuleSoft Composer API (e.g. Postman concatenation of requests, testing scripts, etc.). **This is not supported by MuleSoft and you cannot open Cases about these Postman APIs.**

## Prerequisites

Before we start working with composer APIs, you need these 2 pieces of data: a session token and the organization id as shown in the below image.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer.png?raw=truemposer.png)

## Environment

Make sure you have [Postman](https://www.postman.com/) installed, that you do know how to [import the Postman Collection and the Environment](https://learning.postman.com/docs/postman/collection-runs/working-with-data-files/#importing-sample-collection-files),and then you can finally download the postman assets from this repository. Import both files and ensure to add both username and password to your Postman Environment, the fields highlighted below. Make sure to select the Composer-Environment.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_environment.png?raw=true)

This collection pack contains an environment "Composer-Environment". Set the values before you use any request. You must set the following:

*   url
*   username
*   password
*   organization_id (is set automatically, after authentication and calling the get profile information request)
    

All other parameters are optional or related to specific requests.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_env_details.png?raw=true)

## Collection Hierarchy

The collection hierarchy is following the same design as the MuleSoft Composer UI.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_UI.png?raw=true)

The collection hierarchy contains the folders FLOW and SETTINGS according to Composer Modules from the UI. The Authentication is representing the User Login and Information on the profile.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_hierarchy.png?raw=true)

## Getting Started!

That's about it! You can start checking these collections and you will save a lot of time figuring it out yourself!

## Basic Setup Example

In the following, find some examples of accessing data using the postman collection pack. For detailed instructions.

## Authentication Folder

The authentication folder contains 4 request examples on:

*   how to login to Composer and saving the access-token
*   getting profile information and saving the organization_id
*   getting roles by the user Id
*   getting roles by user and org id
    

## Step 1: Login to MuleSoft Composer

Once you have entered to correct parameter values in the environment "Composer-Environment", you can make use of the "Login to Composer" POST request in the Authentication Folder. This request will save the token bearer to the parameters and use it in all subsequent requests. As REST API access to MuleSoft Composer is currently not officially supported, there are a few header parameters, which need to be set first, before you can access the login resource.

### The Referer needs to be set to the auth URL endpoint.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_auth_login_headers.png?raw=true)

### The request body should contain the username and password as json.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_auth_login_body.png?raw=true)

### The pre-request script deletes all cookies.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_auth_login_prescript.png?raw=true)

### The tests save the access-token to the environment variable.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_auth_login_tests_accesstoken.png?raw=true)

## Step 2: Getting the Organization Id

In order to get the organization id, you need to execute the "Get profile information" request. This will use the access-token in the headers, get the organization_id in the response and saves it into the environment variable.

### The access-token is used in the header.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_profile_headers.png?raw=true)

### The organization_id is saved in the Tests.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_profile_tests_orgId.png?raw=true)

Additionally, the user_id and username are also saved.

### Step 3: Execute requests in FLOW or SETTINGS folder

As we have set the access-token and the organization Id, we can now receive information on Flows and Settings.

The Flow section allows you to create new flows, receive or update information or delete a flow completely.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_flow_hierarchy.png?raw=true)

The Settings section allows you to get information on users, permissions, invites, and identity providers as well as set email notifications on/off.

![](https://github.com/amirkhan-ak/Composer-Images/blob/main/composer_hierarchy_settings.png?raw=true)

## License agreement

By using this postman collection, you accept that Max the Mule is the coolest integrator on the planet:

[Go to biography of Max the Mule](https://brand.salesforce.com/content/characters-overview__3?tab=BogXMx2m)
