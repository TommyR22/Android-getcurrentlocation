Android-getcurrentlocation
==========================

Example to get current location in Android with google maps api v2 and GPS.
MainActivity show the map,draw <code>ic_launcher</code> icon in current location and show a toast with coordinate.
http://developer.android.com/reference/com/google/android/gms/maps/package-summary.html there are reference for Google Maps to customize your map.
If GPS in disabled, start a intent to choosing setting's GPS.

Setup
==========================

Visit https://developers.google.com/maps/documentation/android/start to obtain your API Key
and config the android project(include google play service lib).

Usage
-------
###in AndroidManifest.xml
These are permission for application for using GPS,INTERNET,INTERNAL STORAGE.

<pre><code>uses-permission android:name="com.example.projectname.permission.MAPS_RECEIVE"
uses-permission android:name="android.permission.INTERNET"
uses-permission android:name="com.google.android.providers.gsf.permission.READ_GSERVICES"
uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"
uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"
uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"
</code></pre>

We must activate OPENGL:

<pre><code>uses-feature android:glEsVersion="0x00020000" android:required="true"
</code></pre>

Insert your API key:

<pre><code>meta-data android:name="com.google.android.maps.v2.API_KEY"
android:value="INSERT HERE YOUR API KEY"
</code></pre>

###in Activity
The time refresh:
<pre><code>protected void onResume() {
    super.onResume();
    locationManager.requestLocationUpdates(provider, 1000, 1, this);  
}
</code></pre>


