# Installing a custom app

Ensure you have latest [platform-tools](https://developer.android.com/studio/releases/platform-tools) installed in the system.

* Enable Developer Mode by tapping `Settings`-&gt;`About Phone`-&gt;`Build Number` multiple times.
* Enable `Settings`-&gt;`Developer options`-&gt;`USB debugging`
* Check if the unit is connected

```text
$ adb devices
List of devices attached
66c4bfea    device
```

* Install app using `adb install <app_name>.apk`

```bash
$ adb install myapp.apk
Performing Streamed Install
Success
```

* Your app should show up in the app launcher's list.

![](../../.gitbook/assets/device-2020-02-14-150633.png)

* To remove the app do `adb remove org.myorg.appname`

```bash
$ adb remove org.myorg.appname
Success
```

