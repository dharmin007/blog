---
title:  "Browsing your Android app’s shared preferences, database and cache files"
---
The *Device File Explorer* that is part of Android Studio 3.x is really good for exploring your preference file(s), cache items or database.
> You can only use an Emulator to explore these files as a real device doesn’t give permission to the */data* directory unless it is a rooted device.

To open up the *Device File Explorer* in Android Studio press `Command + Shift + A` to open the Actions menu and search for “Device File Explorer”.

Select the Emulator that the app is running on. The data you are looking for is located under
> /data/data/\<package-name>

![Files under /data/data/com.dharmin.test](/assets/img/explore_app_storage/browse_app_data_1.png)*Files under /data/data/com.dharmin.test*

### 1. Shared Preferences

When you add something to the SharedPreferences in your app that gets added to a file under
> /data/data/\<package-name>/shared_prefs directory

It looks something like this

![A sample SharedPreferences file](/assets/img/explore_app_storage/browse_app_data_2.png)*A sample SharedPreferences file*

### 2. Cache Files

Apps often cache images or other data. You can request the cache directory from Android using `Context.getCacheDir()`.When you create a file in that directory it shows up under
> /data/data/\<package-name>/cache/\<your-file>

### 3. Database

![](/assets/img/explore_app_storage/browse_app_data_3.png)

As you can see in the screenshot above the database used in your app shows up under
> /data/data/\<package-name>/databases/

You can download this database to your laptop and use the [Sqlite Browser](http://sqlitebrowser.org/) to explore the data in it for debugging.

Being able to explore this data would help quickly figure out bugs that could be related to caching, SharedPreferences or data in the database.