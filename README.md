# ![Alt text](https://appbid.com/img/appbid_logo.png?raw=true "AppBid") AppBid

Our technology helps publishers maximize the value of every impression.
We Increase profits by allowing the leading ad exchanges to compete on your impressions, in real time with Machine learning optimization.

Our system studies your sold ad auctions, selects the highest paying exchange and sets the optimal opt-in price on the right network for each impression of each user to make sure that you will achieve a notable uplift in revenue.

All this happens in milliseconds.

<p align="center"> 
<img src="https://appbid.com/img/appbid_flow.png">
<img src="https://appbid.com/img/appbid_chart.png">
</p>

## Download
Download the newest SDK from [Here](https://www.google.com)


## AndroidManifest.xml

Permissions
```
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
```


Add the following lines under application tag in your Manifest
```
<!-- Chartboost -->
<activity android:name="com.chartboost.sdk.CBImpressionActivity"
    android:excludeFromRecents="true"
    android:hardwareAccelerated="true"
    android:theme="@android:style/Theme.Translucent.NoTitleBar.Fullscreen"
    android:configChanges="keyboardHidden|orientation|screenSize" />

<!-- MoPub -->
<activity android:name="com.mopub.mobileads.MoPubActivity" android:configChanges="keyboardHidden|orientation|screenSize"/>
<activity android:name="com.mopub.mobileads.MraidActivity" android:configChanges="keyboardHidden|orientation|screenSize"/>
<activity android:name="com.mopub.common.MoPubBrowser" android:configChanges="keyboardHidden|orientation|screenSize"/>
<activity android:name="com.mopub.mobileads.MraidVideoPlayerActivity" android:configChanges="keyboardHidden|orientation|screenSize"/>
<activity android:name="com.mopub.mobileads.RewardedMraidActivity" android:configChanges="keyboardHidden|orientation|screenSize"/>

<!-- Flurry Advertising -->
<activity
    android:name="com.flurry.android.FlurryFullscreenTakeoverActivity"
    android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|uiMode|screenSize|smallestScreenSize" />

<!-- Applovin -->
<activity android:name="com.applovin.adview.AppLovinInterstitialActivity" android:configChanges="orientation|screenSize"/>
<activity android:name="com.applovin.adview.AppLovinConfirmationActivity" android:configChanges="orientation|screenSize"/>

<!-- Amazon ads -->
<activity android:name="com.amazon.device.ads.AdActivity" android:configChanges="keyboardHidden|orientation|screenSize"/>


<!-- Unity ADS -->
<activity
    android:name="com.unity3d.ads.adunit.AdUnitActivity"
    android:configChanges="fontScale|keyboard|keyboardHidden|locale|mnc|mcc|navigation|orientation|screenLayout|screenSize|smallestScreenSize|uiMode|touchscreen"
    android:hardwareAccelerated="true"
    android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />
<activity
    android:name="com.unity3d.ads.adunit.AdUnitSoftwareActivity"
    android:configChanges="fontScale|keyboard|keyboardHidden|locale|mnc|mcc|navigation|orientation|screenLayout|screenSize|smallestScreenSize|uiMode|touchscreen"
    android:hardwareAccelerated="false"
    android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />

<!-- InMobi -->
<activity
    android:name="com.inmobi.rendering.InMobiAdActivity"
    android:configChanges="keyboardHidden|orientation|keyboard|smallestScreenSize|screenSize|screenLayout"
    android:hardwareAccelerated="true"
    android:resizeableActivity="false"
    android:theme="@android:style/Theme.NoTitleBar"
    tools:ignore="UnusedAttribute" />

<!-- IronSource -->
<activity
    android:name="com.ironsource.sdk.controller.ControllerActivity"
    android:configChanges="orientation|screenSize"
    android:hardwareAccelerated="true" />
<activity
    android:name="com.ironsource.sdk.controller.InterstitialActivity"
    android:configChanges="orientation|screenSize"
    android:hardwareAccelerated="true"
    android:theme="@android:style/Theme.Translucent" />
<activity
    android:name="com.ironsource.sdk.controller.OpenUrlActivity"
    android:configChanges="orientation|screenSize"
    android:hardwareAccelerated="true"
    android:theme="@android:style/Theme.Translucent" />
```


## Usage & Implementation

#### Prerequisites
* Minimum SDK - 16
* Internet permission

#### Usage & Implementation
1. Open your project in the Unity editor.
2. Navigate to Assets -> Import Package -> Custom Package.
3. Select the AppBidPlugin.unitypackage file.
4. Import all of the files for the plugins by selecting Import. Make sure to check for any conflicts with files.


#### Loading & Showing Ads

The easiest way to load&show ads is using the following method - 

```
Appbid.loadWithAutoShow();
```

This, as the signature suggests, loads an ad and show it as soon as it's ready.

Alternatively, you may load an ad and then show it when you see fit - 
```
Appbid.load();
```

And - 
```
Appbid.showLoadedAd();
```

It's worth mentioning that if you call ```
Appbid.load()
``` followed by ```
Appbid.showLoadedAd()```, when the ad isn't ready yet, then the SDK will show the ad once it's loaded.

#### Listener
Implement the following interface to listen to AppBid events - 

```java

public interface AdListener {
    void onAdLoaded();
    
    void onAdFailed();
    
    void onAdOpened();
    
    void onAdClicked();
    
    void onAdClosed();
}
```
Use it as such - 
```java
Appbid.setAdListener(...);
```

One useful usecase for using the listener is loading an ad and showing it when it's ready - 
```java
AppBid.setAdListener(new AdListener() {
    @Override
    public void onAdLoaded() {
        AppBid.showLoadedAd();
    }

    @Override
    public void onAdFailed() {

    }

    @Override
    public void onAdOpened() {

    }

    @Override
    public void onAdClicked() {

    }

    @Override
    public void onAdClosed() {

    }
});

AppBid.load();
```


    




