
## The Problem

Consider the product WCA ([[What is WiseCloud Accessor]]). It is a product used to access CargoWise. When our customers open the app, they are using their own computing power to run the logic of WCA (or the client portion at least).

WiseTech itself is self hosted and therefore a user of WCA. But 
1) We want slightly different configurations when we give our customers. For example, we have our own AD, where to get RDP sign certificates, defaults for legacy/token authentication, etc.
2) On top of this we would like to get to functionally test WCA with real customers before rolling out changes to customers.
## The Solution

To solve both these problems, we create "deployment environments" known simply as "environments". Customer WCA is deployed to an environment known as "PROD" (short for production). PROD is a bit of an abstract concept, but it is any WCA related code/config/infrastructure/AD related to running WCA for our customers. For example, we call the code that runs WCA for customers "PROD WCA". The backend for PROD WCA runs on dedicated servers. These are PROD servers.

The version that WTG employees have access to that has features that are still being tested is known as "WCA CORP" (short for corporation). It runs in the CORP environment, on CORP servers with CORP configs.
## SAND

In fact, PROD and CORP are not the only environments. WCA has yet another version also used internally by devs to access their test rigs, which are also customer instances. This version is called SAND (short for SANDCASTLE? or SANDBOX/SANDPIT?). Just like CORP and PROD, SAND is a "production environment" because there are customers that use the product daily and rely on it.

WCA has yet another environment called SANDTEST which is a testing environment for WCA devs to do a practice deployment.

## Beyond WCA

These deployment environments are not at all specific to WCA. Every one of our products has "deployment targets" configured to allow controlled deployment to all environments. But exactly which environments exist changes from application to application.

### Console
Prerequisites: [[What is Console]]

We don't actively set up more cargowise instances for wisetech, we already have one that we use (TODO: Ediprod?). So console only has a SAND and PROD version. When we start using SAND internally, we may stop using SAND for testing and create a new environment for testing.

### Document Utility
Prerequisites: [[What is CargoWise Document Utility]]

Similarly to console there is no need to have a specific version for CORP. We have PROD CDU for use on customers and SAND CDU for beta versions we are still testing.

CDU doesn't have a dedicated server that it is run on. So referring to a deployment version as an "environment" is a bit misleading. For CDU, SAND comes from one proget feed and PROD comes from another.

## Proget
Prerequisites: [[What is Proget]]


