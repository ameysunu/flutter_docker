## Dockerize Flutter Apps
Run your Flutter app in a Docker container for CI/CD testing in Windows 10.

## Getting Started
Start the program in a Docker Container. Open ``example`` folder and run ``flutter doctor``.
</br>
#### No devices connected!
* Connect your physical device to the host and run ``adb devices`` on your host machine.
* Now to connect your devices wirelessly:
```
adb tcpip 5555
```
Go into your phone's WiFi settings> Advanced and then get your current device IP address.
```
adb connect 192.168.1.3 //Replace with your IP
```
* Now run ``adb devices`` again, you should see your device under *List of Devices* as an IP address. You can now disconnect the device connected via USB cable.

* Head into your running Docker console and run ``adb connect 192.168.1.3:5555 ``. **Do replace the IP as per your device IP** and accept the USB debugging on your physical device.

* Now run ``adb devices`` to see your device appear on your Docker console.

* If you get the ``unauthorized`` command on your console, kill the adb server by running ``adb kill-server`` and run the connection command again.

#### Running
Run ``flutter run`` to continue with the rest deployment on your physical device via Docker.