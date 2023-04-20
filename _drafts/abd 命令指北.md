# 使用adb拨打电话：

测试环境：
```json
macOS:12.1
	
Android:
	
abd:
	Android Debug Bridge version 1.0.41
	Version 34.0.1-9680074
```

使用 adb拨打电话:

```shell
adb shell am start -a android.intent.action.CALL -d tel:<phone_number> //<phone_number>是要呼叫的电话号码
```

使用adb自动接听来电:

```shell
adb shell input keyevent KEYCODE_HEADSETHOOK //模拟按下耳机按钮，从而自动接听来电
```

```shell
adb shell setprop persist.sys.tel.autoanswer.ms 2000
```

使用adb挂断电话:

```shell
adb shell input keyevent 6  //在 Android 设备上模拟按下“电源”按钮
```

```shell
adb shell input keyevent KEYCODE_ENDCALL //模拟按下“挂断”按钮
```

