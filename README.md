# frida
1. Download and install the device on genymotion
2. Install frida and objection tools

python -m pip install Frida
python -m pip install frida-tools
python -m pip install objection
or
pip install Frida
pip install frida-tools
pip install objection

3. Download adb platform tools

4. Download frida injection script

5. Connect device to adb

//adb connect <ip of device:port>

  6.Download frida server for supported android device’s arch version

  7. To find out arch version of device

adb shell getprop ro.product.cpu.abi

  8. Install the target application in the device.

  9. Push frida-server into device:

//adb push <path of frida-server folder><space></data/local/tmp>
10. Give permissions to frida-server:

adb shell chmod 777 /data/local/tmp/frida-server

  11. Setup burpsuite

  12. Pushing the proxy’s CA Certificate

// adb push <path to cacert.der> /data/local/tmp/cert-der.crt
13. Push fridascript.js into device:

//adb push <path to fridascript.js folder> /data/local/tmp
14. Check and run frida server in device

adb shell /data/local/tmp/frida-server &
15. List all running processes on device:

frida-ps -U

  
  16.Locate your application’s package name

  17. Hook fridascript.js into target application

//frida -U -f <your_application_package_name> -l <path_to_fridascript.js_on_your_computer> --no-paus
18. Intercept traffic in BurpSuite.
