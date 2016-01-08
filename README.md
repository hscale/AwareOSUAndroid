# AwareOSU Android Application

### [What is AwareOSU?](https://github.com/CailinPitt/AwareOSU#awareosu)

# News

Development began December 2015, with a planned release date in February 2016.

# Features
* Retrieve crime information from around the university area using [jsoup](http://jsoup.org/)
* Search crime information for specific days
* View crime locations on Google Map
* Choose whether to receive daily reminder to read crime information

# What's going on with the code?

### There are three activities:
* SplashScreen
  * First screen the user is presented with, displays white background with AwareOSU logo on top. The purpose of this screen is to web scrape crime information in the background, then pass the information to MyActivity (the main activity).

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/splash.png" alt="Splash Screen" width="250" height="445"/>

* MyActivity
  * Second screen the user is presented with, displays crime information and allows user to view map of crime locations, choose date to view crime information, or access settings page.

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/main.png" alt="Main Activity" width="250" height="445"/>

* UserSettingsActivity
  * Settings activity, allow user to specify notification preference.

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/settings.png" alt="Settings" width="250" height="445"/>

### And two fragments:
* DatePickerFragment
  * Allows the user to search for crime information for a specific day. This fragment is implemented in a DialogFragment. When the user selects a day to view, this fragment quickly web scrapes the crime information for that specific day and updates MyActivity with the requested information.

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/datePicker.png" alt="Date Search" width="250" height="445"/>

* MapFragment
  * This fragment displays crime locations on a Google Map.
  * One thing to point out is that AwareOSU uses the [Geocoder class](http://developer.android.com/reference/android/location/Geocoder.html) in order to convert street addresses into latitude and longitude to be used for the map. However, Geocoder fails to convert every address (ex. cannot handle street intersections), which means sometimes locations will be missing from MapFragment.

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/map.png" alt="Map" width="250" height="445"/>

## Error handling
* AwareOSU handles different error situations

  * No crimes available:

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/noLoad.png" alt="No Crimes" width="250" height="445"/>

  * Website down:

    <img src="https://raw.githubusercontent.com/CailinPitt/AwareOSUAndroid/master/Images/down.png" alt="Website Down" width="250" height="445"/>
