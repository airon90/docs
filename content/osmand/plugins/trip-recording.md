---
title: "{% data variables.android-values.record_plugin_name %}"
intro: "Essential tool that allows user to record his track using phone's GPS"
versions: '*'
---

<!-- OsmAnd Trip recording plugin is an essential tool for runners, sportsmen and tourists. It allows you to record your movement using your phone's GPS (and through other networks optionally). If you are going for a run, need to see your entire route after a walk around the city or measure the distance you covered, the plugin will help you.

![Trip recording](/assets/images/plugins/placeholder-intro.png)

## How to use

{% link_in_list /how-to-use-android %}
{% link_in_list /how-to-use-ios %}

## Trip recording settings

{% link_in_list /settings-android %}
{% link_in_list /settings-ios %}

## Troubleshooting -->

The Trip recording plugin enables functionality to record and save users tracks.

![Enable / Disable Plugin](/assets/images/plugins/enable_disable_plugin.png)

## Enable / Disable Plugin

In order to Enable / Disable plugin please use:

{% data variables.product.android_button_seq %} {% data variables.android-values.shared_string_menu %} → {% data variables.android-values.plugins_menu_group: %} → choose The Trip recording plugin → tap on the plugin or tap three vertical dots.

{% data variables.product.ios_button_seq %} {% data variables.ios-values.menu %} → {% data variables.ios-values.res_mapsres %} → tab {% data variables.ios-values.plugins %} → {% data variables.ios-values.product_title_track_recording %} → tick the button

> **_Note:_** [Trip recording (REC) widget](https://docs.osmand.net/en/main@latest/osmand/widgets/action-widgets#trip-recording-rec-widget) is required to use Trip recording feature.

## Trip recording Plugin settings for Android

To configure settings follow {% data variables.android-values.shared_string_menu %} → {% data variables.android-values.plugins_menu_group: %} → tap the Trip recording plugin

![REC Settings Plugin](/assets/images/plugins/trip-recording/rec_settings_plugin.png)

### Configure trip recording profile

Default 'Trip recording' profile is Browse map profile. User can choose other OsmAnd profile or create his own (Manage<!--сделать ссылку на инстукцию как сделать уникальный профиль [Manage profile ](text)-->) profile.

![REC profile](/assets/images/plugins/trip-recording/rec_plugin_change_profile.png)

To change the profile please click the globe icon in the upper-right corner.

### Configure trip recording navigation

![REC navigation](/assets/images/plugins/trip-recording/rec_plugin_navigation.png)

Auto-record track during navigation – the function that enables saving each 'trip recording' track automatically. <br>
User may find his track under {% data variables.android-values.shared_string_menu %} → {% data variables.android-values.shared_string_my_places %} → {% data variables.android-values.shared_string_gpx_files %} tab

> :warning: **Track recording impacts the battery life**. Even if the screen is off, it continues to run. Check the notifications in the background in status bar!

Logging interval during navigation controls the frequency of queries to the GPS sensor along with the frequency of new dots appearing in the track line. <br>
By default, it is set to 5 seconds, but it can be configured in the range from 0 seconds to 5 minutes.

### Configure trip recording logging accuracy

![REC logging accuracy](/assets/images/plugins/trip-recording/rec_plugin_logging_accuracy.png)

| Parameter | Description |
|--------------------------|-------------|
| General logging interval |Specifies the logging interval for the general track recording. Can be set to 'always ask' or optionally chosen in the range between 0 to 5 minutes. Can be turned on via [Trip recording (REC) widget](https://docs.osmand.net/en/main@latest/osmand/widgets/action-widgets#trip-recording-rec-widget). |
| Minimum displacement | Specifies the minimum displacement for the track recording. Can be chosen as 'not selected' or optionally chosen from 2 meters  to 50 meters.  This function should be configured to avoid duplicating points being recorded where too little actual motion may have occurred. |
| Minimum accuracy | Accuracy means the proximity of  measurements to the actual position. It is not directly related to precision, which is the spread of repeated measurements. Lowering the accuracy range value may reduce the amount of points recorded depending on GPS signal quality. |
| Minimum speed | Used to filter out the points while object is not moving or moving with a low speed. By using this option User may eliminate recording the bunch of points during the stop time and make resulting track look smoother on the map. |
| Auto-split recording after gap | When enabled, enforces new segment start after 6 minutes gap, new track start after 2 hours gap, new file start when date changed. |
| Prevent standalone logging | When enabled - disables track recording when the app is stopped. In this case, the OsmAnd background indication will disappear from the Android's notification bar.  |
| Include heading | Enables saving of the heading to each track point recorded. |   


> **_TIP:_**
> Set 5 meters distance for 'Minimum displacement' function if there is no need to capture precise data while not moving.

> **_TIP:_**
> It is hard to predict the set of data that will be recorded. If the user is not sure about GPS signal quality it makes sense to turn off (not select) the 'Minimum accuracy' filter.

> **_TIP:_**
> Try to disable 'Minimum displacement' first (set to 'Not selected'). It will help you not to lose data.  If the resulting track looks noisy, try non zero value for this parameter and also raise 'Minimum speed'.

### Configure trip informational settings

![REC informational settings](/assets/images/plugins/trip-recording/rec_plugin_info_settings.png)

**Track storage folder**

Is used to define where the tracks will be stored. There are two options:

- Record tracks to 'rec' folder
- Store recorded tracks in monthly folder

> **_Note:_** User can find his tracks in {% data variables.android-values.shared_string_menu %} → {% data variables.android-values.shared_string_my_places   %} → {% data variables.android-values.shared_string_gpx_files %} tab.

**Notification**

Displays system notification allowing to start trip recording.

**Online tracking**

Allows sharing current location using trip recording.

- Web address 
- Tracking interval - Allows user to specify online tracking interval from 0 seconds to 5 minutes.
- Time buffer - Allows user to specify a time buffer that will keep locations for certain period of time when Internet connection lost.

**Configure trip general settings**

![REC general settings](/assets/images/plugins/trip-recording/rec_plugin_general_settings.png)

- The track folder will redirect user to {% data variables.android-values.shared_string_gpx_files %} tab in {% data variables.android-values.shared_string_menu %} → {% data variables.android-values.shared_string_my_places  %}
- 'Reset plugin settings to default'  - resets all plugin settings to default values. All user settings for this plugin will be lost!
- 'Copy from another profile' - copies plugin settings from another profile.


# From widget
 Before recording the trip a Trip recording settings to be defined. Trip recording settings menu is displayed when user clicks on the REC widget. <br>

![Trip recording (REC) Settings](/assets/images/plugins/trip-recording/rec_settings.png)

In the REC settings menu user can enable 'Show track' on the map feature and configure the style of the track line (for Android only). <br>

The 'Line configuration button' (for Android only) next to the toggle button 'Show track on the map' switcher gives the user an opportunity to change track appearance. User may change the color, width and enable/disable direction arrows, enable show start and finish icons. <br>

Optionally, user can configure Custom width by moving slider from 1 to 24. <br>


![Trip recording Appearence](/assets/images/plugins/trip-recording/appearance_trip_recording.png)

In the REC Settings menu user can configure the logging interval from 0 seconds to 5 minutes. <br>
The Logging interval controls the frequency of queries to the GPS sensor along with frequency of new dots appearing in the track line. <br>

![Logging interval in Trip recording Appearence](/assets/images/plugins/trip-recording/logging_interval_in_tr_widget.png)

If a user wants to apply all configurations to all others tracks recorded in future, the toggle button (switcher) ‘Always ask’ should be off. Please leave this switcher in 'on' position to be able to configure tracks individually. <br>
When all settings are defined, user can push the ‘Start recording’ button.


The Logging interval can be additionally checked/ changed in: <br>
{% data variables.android-values.shared_string_menu %} → {% data variables.android-values.configure_profile %} → {% data variables.android-values.shared_string_trip_recording %} → {% data variables.android-values.save_track_interval %}. <br>
 Menu – Configure profile – Trip recording – Logging interval during navigation <br>

When all settings are configured, press ‘Start recording’ button.
***For Android devices*** the REC widget will change to the red circle.  The distance passed will be displayed in the widget.  
![REC widget](/assets/images/plugins/trip-recording/rec_widget.png)

To tap REC widget again will give an opportunity  to:
* See all general information about the track: distance, ascent, descent, average speed, maximum speed, time span. This panel can  be scrolled by the user right and back.
* Enable 'Show track' on the map feature and configure the style of the track line.
* Clear recorded data
* Start new segment
* Save (save the recorded track and change GPX file name)
* Pause and stop recording

User can find his track in {% data variables.android-values.shared_string_menu %} → {% data variables.android-values.shared_string_my_places   %} →  tab {% data variables.android-values.shared_string_gpx_files %} <br>

***For IOS devices*** when the REC widget will change to the red circle, the  distance passed will be displayed in the widget.
To tap REC widget again will give an opportunity  to:
* Stop recording - will pause The trip recording. Then pressing the widget again will give and options to 'Continue recording'
* Show Info - will display statistics data such as speed, route time, uphills/downhills
* Start new segment
* Save current trip - the track will be automatically saved.

User can find his track in {% data variables.ios-values.menu %} → {% data variables.ios-values.menu_my_places %} → tab {% data variables.ios-values.shared_string_tracks %}.

[Track recording issues](https://docs.osmand.net/en/main@latest/osmand/troubleshooting/track-recording-issues) 