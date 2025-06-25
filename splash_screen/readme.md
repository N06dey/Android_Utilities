# Splash Screen in Android

Splash Screen API is one of the feature added after Android 11+ update. It made the use of Splash Scren bit easy but with some limitations. Let's check how can we implement Splash Screen in Android.

## Step 1:
In step 1 we need an Icon to be displayed in Splash Screen.
<strong>Limitation:</strong> The icon used should be in SVG Format in Square Shape.

It doesn't matter the length and width of the SVG file but the shape should be Square.(Tip: Can use Figma to create the icon for this)

## Step 2: 
Import the Vector Asset of of the SVG file in the drawable.
Here, we are using the name of file as:<strong>splash_icon.xml</strong>

```xml
    <vector xmlns:android="http://schemas.android.com/apk/res/android"
        android:width="160dp"
        android:height="160dp"
        android:viewportWidth="160"
        android:viewportHeight="160">

        <path/>
        <path/>

    </vector>
```

## Step 3: (Optional - Yet Important to Understand)
Group the element of in the splash_icon if there is no Animation being used in the Splash Icon.

```xml
    <vector xmlns:android="http://schemas.android.com/apk/res/android"
        android:width="160dp"
        android:height="160dp"
        android:viewportWidth="160"
        android:viewportHeight="160">

        <group>
            <path/>
            <path/>
        </group>

    </vector>
```

## Step 4: 
Setting up the theme - Necessary to define the theme for the Splash Screen and Theme used Post Splash Screen.

```xml
    <style name="Theme.TestApplication.Starting" parent="Theme.SplashScreen">
        <item name="windowSplashScreenBackground">@color/white</item>
        <item name="postSplashScreenTheme">@style/Theme.TestApplication</item>
        <item name="android:windowSplashScreenAnimatedIcon">@drawable/splash_icon</item>
    </style>
```

<strong>Note:</strong> Android Implementation for Android 31+ is different for implementaion of Theme will differ for for till 30 and 31+. So, style(31+) needs to be created for handling such issues.

## Step 5:
Updating the Manifest file.
- On current condition the Manifest file is set with the theme used in the MainActivity and the Application
- Update the initial starting theme with the Splash Screen theme in the Activity and the Application.

```xml
    android:theme="@style/Theme.TestApplication.Starting"
```

It needs to be updated for Application and activity both. Now, run the application it with show the well defined Splash Screen flash.

## Output Video:

<video width="640" height="360" controls>
  <source src="https://developer.android.com/static/images/guide/topics/ui/splash-screen/cached-ui-indicators.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>