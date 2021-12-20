# Walkthrough

## Steps

1. Begin by running the entire "Before the HOL"

    In this step, you will deploy the VMs for SQL Server and the Web
    No matter what subscription you are on, this should work as expected/outlined

    The tool will generate:
    - Web VM with a working IIS website for Parts Unlimited as of .Net Framework 4.8
    - SQL Server VM with a working SQL Server 2008 with the Parts Unlimited site deployed to it

1. Ensure you completed the scripts for getting the deployment of the web done (the guides will ask you to do that later but it's easier to do it up front).

1. Begin the Hands-on-lab

1. The migration project is a bit tricky.  At times, you won't see your project.  You must add your tools to your project.  

1. When you migrate the web, it deploys to Azure App Service on premium, you'll want to downgrade to Standard

1. With most subscriptions not Pay-as-you-go, you simply won't be able to do the server migration.  

    Instead, just create a full, copy-only backup, restore locally on your machine, create a bacpac file, upload to storage, then import to a new database at Azure.  You can likely use the Parts database that was provisioned.  Optionally, you could downgrade the parts database to basic to save money (it's currently standard).

    Another approach is to delete the parts database and create a simple basic database to save money.

1. Once you have the database restored at Azure, and you have the web solution migrated, you are done with the first part of the "app modernization".  

1. At this point, you should have a working web application and you should have a deployed database with data in it.  You should also have added the connection string to the app service.

2. For the GitHub actions, the deployment workflow is not correct.  






