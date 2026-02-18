
## The Problem

Consider the product WCA ([[What is WiseCloud Accessor]]). It is a product used to access CargoWise. When our customers open the app, they are using their own computing power to run the logic of WCA (or the client portion at least).

WiseTech itself is self hosted and therefore a user of WCA. But 
1) We want slightly different configurations when we give our customers. For example, we have our own AD, where to get RDP sign certificates, defaults for legacy/token authentication, etc.
2) On top of this we would like to get to functionally test WCA with real customers before rolling out changes to customers.
## The Solution

To solve both these problems, we create "deployment environments" known simply as "environments". Customer WCA is deployed to an environment known as "PROD" (short for production). PROD is a bit of an abstract concept, but it is any WCA related code/config/infrastructure related to running WCA for our customers. For example, we call the code that runs WCA for customers "PROD WCA". The backend for PROD WCA runs on dedicated servers. These are PROD servers.

The version that WTG employees have access to that has features that are still being tested is known as "WCA CORP" (short for corporation). It runs in the CORP environment, on CORP servers with CORP configs.
## SAND

In fact, PROD and CORP are not the only environments. WCA als o