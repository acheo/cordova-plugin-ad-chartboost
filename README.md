Cordova Chartboost plugin
====================
# Overview #
Show chartboost interstitial (static interstitial, video interstial), more apps, rewarded video ad

[android, ios] [cordova cli] [xdk] [cocoon] [phonegap build service]

Requires chartboost account https://www.chartboost.com

Android SDK 7.0.1<br>
iOS SDK 7.0.4<br>

This is open source cordova plugin.

Test mode setting:<br>
https://www.chartboost.com - Login - DASHBOARD - [specific app] - APP SETTINGS - Basic Settings - Test Mode: select Disabled or Enabled 

# API #
```javascript
var appId = "REPLACE_THIS_WITH_YOUR_APP_ID";
var appSignature = "REPLACE_THIS_WITH_YOUR_APP_SIGNATURE";
/*
var appId;
var appSignature;
//android
if (navigator.userAgent.match(/Android/i)) {
	appId = "REPLACE_THIS_WITH_YOUR_APP_ID";
	appSignature = "REPLACE_THIS_WITH_YOUR_APP_SIGNATURE";
}
//ios
else if (navigator.userAgent.match(/iPhone/i) || navigator.userAgent.match(/iPad/i)) {
	appId = "REPLACE_THIS_WITH_YOUR_APP_ID";
	appSignature = "REPLACE_THIS_WITH_YOUR_APP_SIGNATURE";
}
*/

document.addEventListener("deviceready", function(){
	window.chartboost.setUp(appId, appSignature);
	//
	window.chartboost.onInterstitialAdPreloaded = function(location) {
		alert('onInterstitialAdPreloaded: ' + location);
	};
	window.chartboost.onInterstitialAdLoaded = function(location) {
		alert('onInterstitialAdLoaded: ' + location);
	};
	window.chartboost.onInterstitialAdShown = function(location) {
		alert('onInterstitialAdShown: ' + location);
	};
	window.chartboost.onInterstitialAdHidden = function(location) {
		alert('onInterstitialAdHidden: ' + location);
	};
	//
	window.chartboost.onRewardedVideoAdPreloaded = function(location) {
		alert('onRewardedVideoAdPreloaded: ' + location);
	};
	window.chartboost.onRewardedVideoAdLoaded = function(location) {
		alert('onRewardedVideoAdLoaded: ' + location);
	};
	window.chartboost.onRewardedVideoAdShown = function(location) {
		alert('onRewardedVideoAdShown: ' + location);
	};
	window.chartboost.onRewardedVideoAdHidden = function(location) {
		alert('onRewardedVideoAdHidden: ' + location);
	};	
	window.chartboost.onRewardedVideoAdCompleted = function(location) {
		alert('onRewardedVideoAdCompleted: ' + location);
	};
}, false);

/*
location parameter:
'Default' - Supports legacy applications that only have one "Default" location
'Startup' - Initial startup of game.
'Home Screen' - Home screen the player first sees.
'Main Menu' - Menu that provides game options.
'Game Screen' - Game screen where all the magic happens.
'Achievements' - Screen with list of achievements in the game.
'Quests' - Quest, missions or goals screen describing things for a player to do.
'Pause' - Pause screen.
'Level Start' - Start of the level.
'Level Complete' - Completion of the level
'Turn Complete' - Finishing a turn in a game.
'IAP Store' - The store where the player pays real money for currency or items.
'Item Store' - The store where a player buys virtual goods.
'Game Over' - The game over screen after a player is finished playing.
'Leaderboard' - List of leaders in the game.
'Settings' - Screen where player can change settings such as sound.
'Quit' - Screen displayed right before the player exits a game.
*/

//static interstitial, video interstitial
window.chartboost.preloadInterstitialAd('Default');//option, download ad previously for fast show
window.chartboost.showInterstitialAd('Default');

window.chartboost.preloadRewardedVideoAd('Default');//option, download ad previously for fast show
window.chartboost.showRewardedVideoAd('Default');

alert(window.chartboost.loadedInterstitialAd());//boolean: true or false
alert(window.chartboost.loadedRewardedVideoAd());//boolean: true or false

alert(window.chartboost.isShowingInterstitialAd());//boolean: true or false
alert(window.chartboost.isShowingRewardedVideoAd());//boolean: true or false
```
# Examples #
<a href="https://github.com/cranberrygame/cordova-plugin-ad-chartboost/blob/master/example/basic/index.html">example/basic/index.html</a><br>
