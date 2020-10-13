# Azure IoT - Raspberry Pi connection
> Source: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-kit-node-get-started

* Create an IoT hub.
* Register a device for Pi in your IoT hub.
* Set up Raspberry Pi.
* Run a sample application on Pi to send sensor data to your IoT hub.
---
## Create an IoT hub
[Official Microsoft Source](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-kit-node-get-started#create-an-iot-hub)
1. Sign in to the **Azure portal**.
2. From the Azure homepage, select the **+ Create a resource** button, and then enter IoT Hub in the **Search the Marketplace field**.
3. Select **IoT Hub** from the search results, and then select **Create**.
4. On the **Basics** tab, complete the fields as follows:
	* **Subscription**: Select the subscription to use for your hub.
	* **Resource Group**: Select a resource group or create a new one. To create a new one, select **Create new** and fill in the name you want to use. To use an existing resource group, select that resource group.
	* **Region**: Select the region in which you want your hub to be located. Select the location closest to you. Some features, such as IoT Hub device streams, are only available in specific regions. For these limited features, you must select one of the supported regions.
	* **IoT Hub Name**: Enter a name for your hub. This name must be globally unique. If the name you enter is available, a green check mark appears.
5. Select **Next: Size and scale** to continue creating your hub
6. Select **Next: Tags** to continue to the next screen
7. Select **Next: Review + create** to review your choices. You see omething similar to this screen, but with the values you selected when creating the hub.
8. Select **Create** to create your new hub. Creating the hub takes a few minutes. 

## Register a new device in the IoT hub
1. In your IoT hub navigation menu, open **IoT Devices**, then select **New** to add a device in your IoT hub.
2. In **Create a device**, provide a name for your new device, such as **myDeviceId**, and select **Save**. This action creates a device identity for your IoT hub.
3. After the device is created, open the device from the list in the **IoT devices** pane. Copy the **Primary Connection String** to use later.

## Set up Raspberry Pi
* Hardware, TBD
* ...

## Run a sample application on Pi to send sensor data to your IoT hub
* Use of the [Azure IoT Device SDK](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-sdks) inside the code to connect with the Azure IoT Hub. SDK available in:
	* [.NET](https://www.nuget.org/packages/Microsoft.Azure.Devices.Client/)
	* [C](https://github.com/Azure/azure-iot-sdk-c/blob/master/readme.md#packages-and-libraries)
	* [Java/Maven](https://github.com/Azure/azure-iot-sdk-java/blob/master/doc/java-devbox-setup.md#for-the-device-sdk)
	* [Node.js](https://www.npmjs.com/package/azure-iot-device)
	* [Python](https://pypi.org/project/azure-iot-device/)
	* [iOS](https://cocoapods.org/pods/AzureIoTHubClient)
* Reccomended for the Rasp. Pi: Python, Node.js, (maybe) Java
* Use the `Primary Connection String` to connect/authenticate the device to the IoT Hub and send data to it.
* Basic [simulated device in python](https://github.com/Azure-Samples/azure-iot-samples-python/blob/master/iot-hub/Quickstarts/simulated-device/SimulatedDevice.py)

###### tags: `p3`