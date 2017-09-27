# Exercise 2: Two Cloud Connectors with Neo Environment

## Install a second Cloud Connector

1. Go to https://tools.hana.ondemand.com/#cloud and download the **Cloud Connector** for **Windows (Portable)**. <p></p>
    ![](../../images/scc_install_download.png)

1. Click **I Have Read And Agree** to start the download.<p></p>
    ![](../../images/scc_install_license.png)

1. After the download has finished, open the file by clicking in the bottom left of the browser. <p></p>
    ![](../../images/scc_install_extract.png)

1. Select **Extract To**. <p></p>
    ![](../../images/scc_install_extract_2.png)

1. In the upcoming dialog enter `C:\Users\student\Desktop\scc-portable` as destination path and click **OK**. <p></p>
    ![](../../images/scc_install_extract_to.png)

1. Right-click the Windows icon in the bottom left (see screenshot) und select **Command Prompt** . <p></p>
    ![](../../images/scc_install_open_cmd.png)

1. In the Command Prompt enter `cd Desktop\scc-portable` followed by `changeport.bat 9090` and finally `go.bat`. Now wait until you see the message **Cloud Connector 2.10.1 started on https:<i></i>//localhost:9090**. <p></p>
    ![](../../images/scc_install_start.png)

## Configure second Cloud Connector

1. Open the URL https://localhost:9090 in Chrome.

  > If you see a message **This page isn’t working** together with the error **ERR_INVALID_HTTP_RESPONSE** you have probably entered <b>http</b>://localhost:9090 instead of <b>https</b>://localhost:9090 in the address-bar.

1. Click **ADVANCED**. <p></p>
    ![](../../images/chrome_security_warning_1.png)

1. Click **Proceed to localhost (unsafe)**. <p></p>
    ![](../../images/chrome_security_warning_2.png)

1. Login with `Administrator` and Password `manage`. <p></p>
    ![](../../images/login_scc_with_initial_credentials.png)

1. Enter the current Password again (`manage`) and choose a new one. We recommend to use `welcome` (same as the first Cloud Connector Instance). Press **Save**. <p></p>
    ![](../../images/scc_initial_setup.png)

  > Note: you'll do pretty much the same as in [Exercise 1](../ex1/README.md) with one important difference: This time you'll additionally have to configure a Location ID.

1. Define your subaccount:
    - First Subaccount:
      - Select **hanatrial.ondemand.com** in the dropdown for **Region Host**
      - Enter your **Subaccount Name**, it should be similar to this `p123456789trial`.
      - Enter your **Subaccount User**, it should be similar to this `P123456789`.
      - Enter your Subaccount User **Password**.
      - Enter **Location ID**: `SCC-US`
    - HTTPS Proxy
      - Host: `proxy`
      - Port: `8080`
    - Click **Save** <p></p>
    ![](../../images/define_subaccount_with_loc_id.png)

1. Dismiss the upcoming message by clicking **OK**.

## Import Access Control

1. Click **Cloud To On-Premise** and then the **import icon** (see screenshot blow). <p></p>
    ![](../../images/scc_import_open_dialog.png)

1. Click **Browse**. <p></p>
    ![](../../images/scc_import_press_browse.png)

1. Select **access_control_b.zip** and click **Open**. <p></p>
    ![](../../images/scc_import_select_access_control_b.png)

1. Click **Import**. <p></p>
    ![](../../images/scc_import_press_import_b.png)

1. Click the edit icon of the imported mapping (see screenshot below). <p></p>
    ![](../../images/scc_import_edit.png)

1. Change the **Internal Host** to the hostname of your neighbor and click **Save**. <p></p>
    ![](../../images/scc_import_changeme.png)

1. After changing the **Internal Host** to the hostname of your neighbor verify with the connection check button that you had no typos and your CLoud Connector can reach his ABAP system. <p></p>
    ![](../../images/scc_check_connection.png)

## Import Destination

1. Go back to the Cockpit.

1. Open the Import Destination Dialog
    - Click **Connectivity**
    - Click **Destinations**
    - Click **Import Destination** <p></p>
    ![](../../images/cp_import_press_import_2.png)

1. Select **abapBackend2** and click **Open** <p></p>
    ![](../../images/cp_import_abap_backend_2.png)

1. click **Save**. <p></p>

## Import Sample Application

1. Go back to SAP Web IDE.

1. Go to **File** > **Import** > **From File System**. <p></p>
    ![](../../images/cp_webide_open_import_dialog.png)

1. Click **Browse**. <p></p>
    ![](../../images/cp_webide_import_browse.png)

1. Select the file **html5-complex.zip** and click **Open**. <p></p>
    ![](../../images/cp_webide_import_select_complex.png)

1. Make sure **Import to** is set to `/html5-complex` and click **Ok**. <p></p>
    ![](../../images/cp_webide_import_complex.png)

## Run the App
1. Make sure **html5-complex** is selected, otherwise select it with a single click. Now click the run-icon (see screenshot). <p></p>
    ![](../../images/cp_webide_run_complex.png)

1. You should now see our Demo-Application with data from two ABAP-Backends. <p></p>
    ![](../../images/cp_webide_review_complex.png)
