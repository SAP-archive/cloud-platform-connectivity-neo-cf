# Exercise 1: Cloud Connector with Neo Environment
 
## Configure Cloud Connector

1. Open Google Chrome.

1. In the bookmarks-bar select **SAP TechEd** > **SAP Cloud Connector**. <p></p>
    ![](../../images/bookmark.png)

1. Login to the Cloud Connector Administrator Interface with the following credentials:
    - **User Name**: `Administrator`
    - **Password**: `welcome`
    - Click **Login**. <p></p>
    ![](../../images/login_scc.png)

1. Define your subaccount:
    - Select **hanatrial.ondemand.com** in the dropdown for **Region Host**
    - Enter your **Subaccount Name**, it should be similar to this `p123456789trial`.
    - Enter your **Subaccount User**, it should be similar to this `P123456789`.
    - Enter your Subaccount User **Password**.
    - Click **Save** <p></p>
    ![](../../images/define_subaccount.png)

## Import Access Control

1. Click **Cloud To On-Premise** and then the **import icon** (see screenshot blow). <p></p>
    ![](../../images/scc_import_open_dialog.png)

1. Click **Browse**. <p></p>
    ![](../../images/scc_import_press_browse.png)

1. Select **access_control_a.zip** and click **Open**. <p></p>
    ![](../../images/scc_import_select_access_control_a.png)

1. Click **Import**. <p></p>
    ![](../../images/scc_import_press_import.png)

1. Review that the import was successful. Your screen should look similar to the screenshot below. <p></p>
    ![](../../images/scc_import_review.png)

## Import Destination

1. Navigate to https://hanatrial.ondemand.com/

1. Login to your account <p></p>
    ![](../../images/cp_login.png)

1. Open the Import-Destination-Dialog
    - Click **Connectivity**
    - Click **Destinations**
    - Click **Import Destination** <p></p>
    ![](../../images/cp_import_press_import.png)

1. Select **abapBackend1** and click **Open**. <p></p>
    ![](../../images/cp_import_abap_backend_1.png)

1. Click **Save**. <p></p>

## Import Sample Application

1. Open the SAP Web IDE:
    - Go to **Services**.
    - Search for `SAP Web IDE`.
    - Click the **SAP Web IDE** tile. <p></p>
    ![](../../images/cp_webide_search_service.png)

1. Click **Go to Services**. <p></p>
    ![](../../images/cp_webide_go_to.png)

1. Open the Dev-View as shown below. <p></p>
    ![](../../images/cp_webide_select_dev.png)

1. Go to **File** > **Import** > **From File System**. <p></p>
    ![](../../images/cp_webide_open_import_dialog.png)

1. Click **Browse**. <p></p>
    ![](../../images/cp_webide_import_browse.png)

1. Select the file **html5-simple.zip** and click **Open**. <p></p>
    ![](../../images/cp_webide_import_select_simple.png)

1. Make sure **Import to** is set to `/html5-simple` and click **Ok**. <p></p>
    ![](../../images/cp_webide_import_simple.png)

## Run the App
1. Make sure **html5-simple** is selected, otherwise select it with a single click. Now click the run-icon (see screenshot). <p></p>
    ![](../../images/cp_webide_run_simple.png)

1. You should now see our Demo-Application with data from the ABAP-Backend. <p></p>
    ![](../../images/cp_webide_review_simple.png)