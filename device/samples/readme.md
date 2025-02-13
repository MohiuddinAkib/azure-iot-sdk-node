# Samples for the Azure IoT device SDK for Node.js

## Run samples using GitHub codespaces

You can use Github Codespaces to be up and running quickly! Here are the steps to follow.

**1) Make sure you have the prerequisites**

In order to run the device samples you will first need the following prerequisites:

- An Azure IoT Hub instance. [(Link if you don't.)][https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-create-through-portal]
- A device identity for your device. [(Link if you don't.)][https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-create-through-portal#register-a-new-device-in-the-iot-hub]

**2) Create and open Codespace**

- Select the Codespaces tab and the "New codespace" button

  ![screen shot of create codespace](./media/github-codespace.png)

- Once the Codespace is open, all required packages to run the samples will be setup for you

**3) Set the DEVICE_CONNECTION_STRING environment variable**

- From a shell or Node.js command prompt, navigate to the folder where you placed the sample files.
- Set the `DEVICE_CONNECTION_STRING` environment variable:

```bash
export DEVICE_CONNECTION_STRING="<YourIoTHubConnectionString>"
```

**4) Run it**

Run the sample application using the following commands:

_for JavaScript_

```bash
cd device/samples/javascript
node simple_sample_device.js
```

_for TypeScript_

```bash
cd device/samples/typescript/dist
node simple_sample_device.js
```

## Run samples locally

_How to run a sample in your own folder using published npm packages._

**1) Make sure you have the prerequisites**

In order to run the device samples you will first need the following prerequisites:

- The latest or LTS version of Node.js on your device. (Check out [Nodejs.org](https://nodejs.org/) for more info)
- An Azure IoT Hub instance. [(Link if you don't.)][https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-create-through-portal]
- A device identity for your device. [(Link if you don't.)][https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-create-through-portal#register-a-new-device-in-the-iot-hub]
- Clone this repo to your local machine

**2) Install dependencies**

You need to install proper dependencies as defined in the **package.json**. Run the following commands:

_for JavaScript_

```
cd device/samples/javascript
npm install
```

_for TypeScript_

```
cd device/samples/typescript
npm install
```

**3) Set the DEVICE_CONNECTION_STRING environment variable**

- From a shell or Node.js command prompt, navigate to the folder where you placed the sample files.
- Set the `DEVICE_CONNECTION_STRING` environment variable:

_in bash_

```bash
export DEVICE_CONNECTION_STRING="<YourIoTHubConnectionString>"
```

_in powershell_

```powershell
$env:DEVICE_CONNECTION_STRING="<YourIoTHubConnectionString>"
```

**4) Build it**

For the TypeScript samples, we need to run the `build` command to transpile the TypeScript code into the JavaScript files:

```
npm run build
```

The JavaScript files are placed into the `dist` folder.

**5) Run it**

Run the sample application using the following commands:

JavaScript

```bash
node sample_sample_device.js
```

TypeScript

```bash
cd dist
node sample_sample_device.js
```

## List of available samples

### **Simple send and receive messages...**

| Sample                        | Description                                                                                                                         | JavaScript | TypeScript |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | :--------: | :--------: |
| simple_sample_device          | Connect to IoT Hub and send and receive messages.                                                                                   |     ✔      |     ✔      |
| simple_sample_device_with_sas | Connect using a SAS Token to IoT Hub and send and receive messages.                                                                 |     ✔      |     ✔      |
| simple_sample_device_x509     | Connect using an X-509 certificate to IoT Hub and send and receive messages.                                                        |     ✔      |     ✔      |
| send_batch_http               | Connect to IoT Hub and send a batch of messages over an HTTP connection.                                                            |     ✔      |     ✔      |
| remote_monitoring             | Implements the device code used to connect to an [Azure IoT Suite Remote Monitoring preconfigured solution][remote-monitoring-pcs]. |     ✔      |     ✔      |
| edge_downstream_device        | Connect a downstream device to IoT Edge and send and receive messages.                                                              |     ✔      |     ✔      |
| device_through_proxy          | Connect to IoT Hub and send and recieve messages through a proxy                                                                    |     ✔      |           |

### **Device services samples (Device Twins, Methods, and Device Management)...**

| Sample                     | Description                                                                                                                                                                                                                                             | JavaScript | TypeScript |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: | :--------: |
| simple_sample_device_twin  | Shows how to synchronize a Device Twin with Azure IoT Hub on a device.                                                                                                                                                                                  |     ✔      |     ✔      |
| device_method              | Shows how to implement an Azure IoT Hub Cloud to Device Direct Method on a device.                                                                                                                                                                      |     ✔      |     ✔      |
| dmpatterns_reboot_device   | Shows how a device handles a C2D method to reboot and provides progress updates through twin reported properties. See [device management patterns][dm-patterns] for instructions on running the device management patterns samples.                     |     ✔      |     ✔      |
| dmpatterns_fwupdate_device | Shows how a device handles a C2D method to initiate a firmware update and provides progress updates through twin reported properties. See [device management patterns][dm-patterns] for instructions on running the device management patterns samples. |     ✔      |     ✔      |

### **Plug and play examples**

| Sample                   | Description              | JavaScript | TypeScript |
| ------------------------ | ------------------------ | :--------: | :--------: |
| pnpTemperatureController | Enabling PnP on a device |     ✔      |            |

### **Uploading blob to Azure...**

| Sample                      | Description                                                           | JavaScript | TypeScript |
| --------------------------- | --------------------------------------------------------------------- | :--------: | :--------: |
| upload_to_blob (deprecated) | Uploads a blob to Azure through IoT Hub                               |     ✔      |     ✔      |
| upload_to_blob_advanced     | More advanced scenario for greater control over the blob upload calls |     ✔      |     ✔      |

## Read More

For more information on how to use this library refer to the documents below:

- [Prepare your node.js development environment][node-devbox-setup]
- [Setup IoT Hub][lnk-setup-iot-hub]
- [Provision devices][lnk-manage-iot-hub]
- [Node API reference][node-api-reference]
- [Debugging with Visual Studio Code][debug-with-vscode]
- [Use the iothub-explorer command line tool][iothub-explorer]

[lnk-setup-iot-hub]: https://aka.ms/howtocreateazureiothub
[lnk-manage-iot-hub]: https://aka.ms/manageiothub
[remote-monitoring-pcs]: https://docs.microsoft.com/en-us/azure/iot-suite/iot-suite-remote-monitoring-sample-walkthrough
[node-api-reference]: https://docs.microsoft.com/en-us/javascript/api/azure-iot-device/
[iothub-explorer]: https://github.com/azure/iothub-explorer
[debug-with-vscode]: ../../doc/node-debug-vscode.md
[node-devbox-setup]: ../../doc/node-devbox-setup.md
[dm-patterns]: ../../doc/dmpatterns.md
