# ResponsePath-Config
This app allows for GUI-based visualization and configuration of Response Path (IPSLA) test elements.

## Use Case
It is intended for administrators who want to manage their tests manually, from a central location.
It is context-sensitive and can be used for a group (dashboard) or a specific device (context views).

## Example
![Response Path List Tables](screenshot%231.png)

## Description
Once the context is selected, the user choses a test type and the app will display 2 panes: 
* Tests discovered/monitored by CAPM: These are the tests running on supported network devices, that are collected in CAPM. 
* Test profiles created in CAPM: These are previous Response Path configurations that have been pushed to devices using CAPM.

The tables allows for:
* Export: Exports the currently displayed information to CSV
* Create: Create a new test of the selected type
* Duplicate: Create a new test based on the configuration of an existing test
* Edit: Modify an existing test
* Delete: Remove an existing test (retire from the device, or delete from CAPM database if it's already retired)

![Response Path List Tables](screenshot%232.png)

All supported configuration elements are available to the user depending on the selected test type.
Only valid test hosts are available: 
* They must support Response Path features
* They must have a Monitoring Profile that includes Response Path metric families (and show up as "supported")
* They must have a SNMP Set profile assigned in DA

Response Path tests in the discovered/monitored table have a "Quick View" capability that allows the user to verify that data is being collected and rolled-up as expected.

![Response Path List Tables](screenshot%233.png)

## Installation

### Prerequisites
The app is packed in a ZIP archive and can be installed through CA PM 3.2+ App Deployment function.

### Installation steps
* Download the master zip archive on your workstation
* Under CA PC Administration -> App Deployment, select the zip file and install it.
* Navigate to a dashboard or device context page where you want to add this configuration capability.
* In page editor, add an App View (under External Links) and select "Response Path Configuration" in the app drop down.
* **Users other than admin need to be enabled for DA REST access in CA PC (see https://communities.ca.com/docs/DOC-231174750-ca-pc-apps-and-user-authorization)**

### App view parameters
Default URL (should not need to be changed): index.html?ItemIdDA={ItemIdDA}&ItemTypeName={ItemTypeName}
Parameters:
* ItemIdDA={ItemIdDA} (context device ID or group ID)
* ItemTypeName={ItemTypeName} (page context type)

## Notes
This app is a field development. No support will be provided by CA Support.

