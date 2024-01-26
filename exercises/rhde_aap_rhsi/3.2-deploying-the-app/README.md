# Workshop Exercise 3.2 - Deploying the Application via Ansible Controller

## Table of Contents

* [Objective](#objective)
* [Step 1 -Syncing Our Project](#step-1---syncing-our-project)
* [Step 2 - Creating a Job Tempate](#step-2---creating-a-job-template)
* [Step 3 - Running the Job Template](#step-3---running-the-job-template)
* [Solutions](#solutions)

## Objective

In this exercise, we'll sync our project in Ansible Controller, create a job template, and run our new playbook.

### Step 1 - Syncing Our Project

Return to the Ansible Controller WebUI and navigate to **Resources** > **Projects**. Locate the project named **Device Edge Codebase** and click the **Sync Project** button on the right hand side of the page.

For reference, this is the sync button:
![Sync Button](../images/sync-button.png)

After clicking the sync button, the WebUI will show the project syncing and then a success under the **Status** column.

### Step 2 - Creating a Job Template

In the Controller WebUI. under **Resources** > **Templates**, select **Add** > **Add job template** and enter the following information:

<table>
  <tr>
    <th>Parameter</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Name</td>
    <td>Deploy Application</td>
  </tr>
  <tr>
    <td>Inventory</td>
    <td>Edge Systems</td>
  </tr>
  <tr>
    <td>Project</td>
    <td>Device Edge Codebase</td>
  </tr>
  <tr>
    <td>Execution Environment</td>
    <td>Device Edge Workshops Execution Environment</td>
  </tr>
  <tr>
    <td>Playbook</td>
    <td>playbooks/deploy-app.yml</td>
  </tr>
  <tr>
    <td>Credentials</td>
    <td><li>✓ Device Credentials</li></td>
  </tr>
</table>

Remember to click **Save**.

### Step 3 - Running the Job Template

Now that the job template has been created, click the **Launch** button if you are still within the **Deploy Application** job template. Otherwise, click on the rocket ship on the Templates page to launch the job template. Monitor the output for any errors or issues. However, hopefully the job executes successfully.

As a reminder, the output of jobs can be reviewed on the **Jobs** tab.

Once the job completes, review the output to make sure everything ran successfully. In addition, running `podman ps` on the CLI of the edge device should show more pods running:

![Podman PS](../images/podman-ps.png)

### Solutions

Deploy Application job template:

![Deploy Application Job Template](../images/deploy-app-job-template.png)

---
**Navigation**

[Previous Exercise](../3.1-containerized-app-automation/) | [Next Exercise](../4.1-expose-app-webui/)

[Click here to return to the Workshop Homepage](../README.md)
