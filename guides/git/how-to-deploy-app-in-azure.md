# How to create an Azure Resource Group, Virtual Machine, and Web App, then deploy a ZIP application

## Goal
Create a resource group, deploy a virtual machine (VM), deploy a web app, configure it, and deploy an application using a ZIP file with environment variables and startup settings.

## Prerequisites
- The application ZIP file downloaded locally.

## Steps

1. Go to the Azure portal.
2. Create a Resource Group.
3. After the resource group is created, confirm it is empty.
4. Create a Virtual Machine inside the resource group.
5. In the VM creation form, set the virtual machine name and region.
6. Configure inbound ports and do not leave inbound ports open.
7. (Optional) Add additional items or services to the VM as needed.
8. Select **Review + create**.
9. Wait for **Deployment in progress** and then **Deployment is complete**.
10. Go to the resource group’s Resources list and confirm the VM appears.
11. If you are not using the VM, turn it off.
12. Create a Web App.
13. In the Web App setup, configure the subscription, resource group, and web app name.
14. Set **Publish** to **Code**.
15. Select **Python** as the language.
16. Start the web app deployment.
17. Wait for **Deployment in progress** and then **Deployment succeeded**.
18. Go back to the Resource Group containing the VM and Web App.
19. Select your Web App.
20. Go to **Settings → Environment variables**.
21. Create a new environment variable with name `SCM_DO_BUILD_DURING_DEPLOYMENT` and value `true`.
22. Select **Apply** and confirm the changes.
23. Enable **Auto-start** if available.
24. Go to **Settings → Configuration (Stack settings)**.
25. Add a Startup command.
26. Select **Apply**.
27. In the Web App, go to **Deployment**.
28. Open **Advanced Tools**.
29. Open **File Manager**.
30. Navigate to the `site` folder.
31. Upload the ZIP file into the site directory.

## Notes
- A resource group starts empty until you add resources.
- Creating a VM generates multiple billable resources automatically.
- VMs incur ongoing costs while running.
- Setting `SCM_DO_BUILD_DURING_DEPLOYMENT=true` ensures the app is built during ZIP deployment.
- The application is created from the uploaded ZIP file during deployment.

