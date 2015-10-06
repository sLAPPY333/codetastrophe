# Signal strength #

The native unit of signal strength for Android is **asu**. I have no idea what that stands for. I did find out that you can calculate units in **dBm** with this formula:
```
   dBm = -113 + 2*asu
```
This information was found in `PhoneStateIntentReceiver.java` in the Android source code, which you is available here: http://android.git.kernel.org/?p=platform/frameworks/base.git;a=blob;f=telephony/java/com/android/internal/telephony/PhoneStateIntentReceiver.java;h=c558cd15f1d1de9e702daaccd0bdee6da5e23231;hb=HEAD