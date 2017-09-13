# Exercise 3: Cloud Connector on CF Environment

## Configure Cloud Connector

1. Go back to the SAP Cloud Platform Cockpit.

1. Click **Home**. <p></p>
    ![](../../images/cp_go_home.png)

1. Click **Go to Cloud Foundry Trial**. <p></p>
    ![](../../images/cp_go_cf_trial.png)

1. In the upcoming dialog select the right **Region** based on you location and then click **OK**.<br />(Use the **US East (VA)** for TechEd Las Vegas and **Europe (Frankfurt)** for TechEd Bangalore and Barcelona).<p></p>
    ![](../../images/cf_start_trial.png)

1. After some seconds your CF-trial-subaccount is created. Click **Go to Space**. <p></p>
    ![](../../images/cf_go_to_space.png)

1. From your space navigate to the global-account-level. <p></p>
    ![](../../images/cf_click_globalaccount.png)

1. Click the show details icon (see screenshot). <p></p>
    ![](../../images/cf_show_id.png)

1. Copy your **ID**. <p></p>
    ![](../../images/cf_copy_id.png)

1. Go back to the Cloud Connector Administrator Interface.

1. Click **Add Subaccount**. <p></p>
    ![](../../images/scc_add_subaccount.png)

1. Define your subaccount:
    - Select **cf.us10.hana.ondemand.com** in the dropdown for **Region Host**
    - Paste the ID you just copied in the cockpit as **Subaccount Name**.
    - Enter your **Subaccount User**, for cloud foundry environment it is the email address, which should be similar to `cpl618-XXX@teched.cloud.sap`.
    - Enter your Subaccount User **Password**.
    - Click **Save** <p></p>
    ![](../../images/scc_add_cf_account.png)

## Import Access Control

1. Select the newly added subaccount in the overview-page.
    ![](../../images/scc_select_cf_account.png)

1. Click **Cloud To On-Premise** and then the **import icon** (see screenshot blow). <p></p>
    ![](../../images/scc_import_open_dialog.png)

1. Click **Browse**. <p></p>
    ![](../../images/scc_import_press_browse.png)

1. Select **access_control_a.zip** and click **Open**. <p></p>
    ![](../../images/scc_import_select_access_control_a.png)

1. Click **Import**. <p></p>
    ![](../../images/scc_import_press_import.png)

1. Review that the import was successful. You screen should look similar to the screenshot below. <p></p>
    ![](../../images/scc_import_review.png)

## Create Connectivity Service Instance

1. Go back to the SAP Cloud Platform Cockpit

1. Navigate into your subaccount. <p></p>
    ![](../../images/cf_click_subaccount.png)

1.  Navigate into your **dev** space. <p></p>
    ![](../../images/cf_click_dev_space.png)

1. Open the **Service Marketplace**. <p></p>
    ![](../../images/cf_open_service_marketplace.png)

1. Find and click the **connectivity** tile. <p></p>
    ![](../../images/cf_connectivity_tile.png)

1. Click **Instances** followed by **New Instance**. <p></p>
    ![](../../images/cf_connectivity_new_instance.png)

1. Press **Next** three times. <p></p>
    ![](../../images/cf_connectivity_new_instance_next.png)

1. Enter the **Instance Name**: `connectivity-demo-lite` and click **Finish**. <p></p>
    ![](../../images/cf_connectivity_instance_name.png)


## Create XSUAA Service Instance

1. Click the arrow next to **connectivity** (see screenshot) and select **xsuaa**. <p></p>
    ![](../../images/cf_xsuaa_goto.png)

1. Click **New Instance**. <p></p>
    ![](../../images/cf_xsuaa_new_instance.png)

1. Press **Next** only once.

1. Press **Browse**.<p></p>
    ![](../../images/cf_xsuaa_browse.png)

1. Select the **xsuaa-parameters.json** file and press **Open**.<p></p>
    ![](../../images/cf_xsuaa_select_parameters.png)

1. Verify that the json was loaded successfully (see screenshot) and click **Next** twice.<p></p>
    ![](../../images/cf_xsuaa_check_parameters.png)

1. Enter the **Instance Name**: `xsuaa-demo` and click **Finish**. <p></p>
    ![](../../images/cf_xsuaa_instance_name.png)

## Create Application Manifests

1. Open the students share and drag the files **connectivity-app-demo-manifest.yml** and **approuter-manifest.yml** to your Desktop. This will create a local copy of the files. <p></p>
    ![](../../images/cf_edit_manifest_create_copy.png)

1. Right-click the **connectivity-app-demo-manifest.yml** file on your **Desktop** and select **Edit with Notepad++**. <p></p>
    ![](../../images/cf_edit_manifest_open_connectivity.png)

1.  Add your username as suffix to the host as highlighted in yellow in the screenshot and click the save icon.<p></p>
    ![](../../images/cf_edit_manifest_save_connectivity.png)

1. Right-click the **approuter-manifest.yml** file on your **Desktop** and select **Edit with Notepad++**. <p></p>
    ![](../../images/cf_edit_manifest_open_approuter.png)

1.  Add your username as suffix to the host and the destination-url as highlighted in yellow in the screenshot and click the save icon.<p></p>
    ![](../../images/cf_edit_manifest_save_approuter.png)

## Deploy the Approuter

1. Back in the Browser click the **dev**-space, **Applications** followed by **Deploy Application**. <p></p>
    ![](../../images/cf_click_deploy_application.png)

1. Click **Browse** and select **approuter.zip** as **File Location**. Now **Browse** to select the **Manifest Location** and select the **approuter-manifest.yml** from your Desktop and click **Deploy**. <p></p>
    ![](../../images/cf_deploy_approuter.png)

## Deploy and test the Application

1. Click **Deploy Application** once again.

1. Click **Browse** and select **connectivity-app-demo.war** as **File Location**. Now **Browse** to select the **Manifest Location** and select the **connectivity-app-demo-manifest.yml** from your Desktop and click **Deploy**. <p></p>
    ![](../../images/cf_deploy_connectivity.png)

1. Wait until both your applications show a green **Started** as State and then click on **approuter-demo**. <p></p>
    ![](../../images/cf_wait_for_deployment.png)

1. Navigate to the Approuter by clicking the link as shown in the screenshot. <p></p>
    ![](../../images/cf_start_app.png)

1. Login using the E-Mail-Address and password of your trial account. <p></p>
    ![](../../images/cf_loginto_app.png)

1. Replace `/index.html` with `/app/` in the address-bar of the browser.<p></p>
    ![](../../images/cf_nav_to_app.png)

1. Once again you should now see our app with data from you local ABAP-system.<p></p>
    ![](../../images/cf_review_app.png)
