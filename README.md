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

## Usage & Implementation

#### Prerequisites
* Minimum SDK - 16
* Internet permission

#### Usage & Implementation
1. Open your project in the Unity editor.
2. Navigate to Assets -> Import Package -> Custom Package.
3. Select the AppBidPlugin.unitypackage file.
4. Import all of the files for the plugins by selecting Import. Make sure to check for any conflicts with files.

#### Usage & Implementation
In unity open AppBidSettings (Resoucres/AppBidSettings) and set your AppBid Key

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
Add listeners to listen to AppBid events (if need):

```
AppBid.AdLoaded += AdLoaded;
AppBid.AdClosed += AdClosed;
AppBid.AdFailed += AdFailed;
AppBid.AdClicked += AdClicked;
AppBid.AdOpened += AdOpened;
```

One useful usecase for using the listener is loading an ad and showing it when it's ready - 
```
AppBid.AdLoaded += AdLoaded;
...
void AdLoaded ()
{
  AppBid.ShowLoadedAd();
}
...
AppBid.load()

```


