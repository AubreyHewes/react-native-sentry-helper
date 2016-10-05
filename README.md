# react-native-sentry-helper

Just adds a Sentry (Raven) `EventBuilderHelper` with all/any possible tags

i.e.
 * APP_VERSION
 * PLATFORM
 * Platform Meta
   * depends on platform and due to WIP
 
etc

## Currently Android only

````java

    // app vars
    
    constants.put("APP_BUILD", BuildConfig.DEBUG ? "DEBUG" : "RELEASE");
    constants.put("APP_VERSION", BuildConfig.VERSION_NAME);
    //constants.put("APP_VERSION_CODE", BuildConfig.VERSION_CODE);
    
    // most should be removed when the android sentry lib is available
    
    constants.put("PLATFORM", "Android"); // sic .. should be removed when the android sentry lib is working
    constants.put("UDID", getDeviceID());
    constants.put("UUID", getUserID());
    constants.put("SDK_INT", Build.VERSION.SDK_INT);
    constants.put("RELEASE", Build.VERSION.RELEASE);
    constants.put("INCREMENTAL", Build.VERSION.INCREMENTAL);
    constants.put("CODENAME", Build.VERSION.CODENAME);
    constants.put("DISPLAY", Build.DISPLAY);
    constants.put("BRAND", Build.BRAND);
    constants.put("SERIAL", Build.SERIAL);
    constants.put("DEVICE", Build.DEVICE);
    constants.put("HARDWARE", Build.HARDWARE);
    constants.put("FINGERPRINT", Build.FINGERPRINT);
    constants.put("BUILD ID", Build.ID);
    constants.put("MANUFACTURER", Build.MANUFACTURER);
    constants.put("MODEL", Build.MODEL);
    constants.put("PRODUCT", Build.PRODUCT);
    constants.put("BOARD", Build.BOARD);
    constants.put("BOOTLOADER", Build.BOOTLOADER);
    constants.put("RADIO", Build.getRadioVersion());

    // some need extra inputs.. let's try to give them their input
    
    if (isRunningOnGenymotion()) {
      constants.put("GENYMOTION", true);
    }

    if (isRunningOnStockEmulator()) {
      constants.put("EMULATOR", true);
    }
    
````

For native usage apply the `react-native` constants to your `EventBuilderHelper`


### WIP Moving from BitBucket
