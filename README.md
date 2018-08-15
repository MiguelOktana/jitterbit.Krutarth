You can have to types of Enviroments, new ones or the used in the development of the project. 
In both cases you have an Org A and Org B called origin and destination respectivelyin direct sync. 
In the reverse sync Org A is the destination and B the origin.

## Table of Contents

* [Dependencies](#dependencies)
* [Installation](#installation)
* [Create URL Harmony API](#Create-URL-Harmony-API)
* [Modifying the PostClient class code](#Modifying-the-PostClient-class-code)
* [Copy the trigger code](#Copy-the-trigger-code)

## Dependencies

* Jitterbit Studio https://success.jitterbit.com/display/DOC/Design+Studio
* An harmony account https://www.jitterbit.com/harmony/


## Installation

1. Clone [this](https://github.com/MiguelOktana/jitterbit.Krutarth.git) repository to a local directory.

2. In Jitterbit Studio Import the project from filesystem.

3. Deploy the project to you Hermony account.

4. Create the Harmony API urls (see next section).

5. Modify the PostClient class with the urls in step 4.

6. Insert or modify a Contact to sync.


## Create URL Harmony API

1. Log in your Harmony account.

2. go to API Manager. 

3. Click on "Create & Publish New".

4. Fill the form.

5. Select the project created in the Studio, as operation select "DIRECT Query Accounts" or "INVERT Query Accounts".

6. Select POST as Method.

7. Select 'No Response' as Response Type.

8. Assign the operation and click next.

9. If you do not have an Profile, create one and select it, then assign and click next.

10. Click 'Save and Publish' Button.

You need one api url for each operation, in this case you need two. You need this urls in the section
"Modify the PostClient".


## Modifying the PostClient class code

1. Modify the call to the Harmony API. In Org A put the value for "DIRECT Query Accounts" and in Org B put the value for "INVERT Query Accounts"


## Copy the trigger code 

In the case you need to run the project using two fresh org, you need to copy the trigger over Contact in both Orgs, but be careful.
If you are using the orgs in the documentation don't follow the next steps.

1. In Org A (called origin org) the trigger is on insert and update.

2. In Org B (destination org) the trigger is only on update.

3. Copy the class PostClient to the orgs A nad B.



