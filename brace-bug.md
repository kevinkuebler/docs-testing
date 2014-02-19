---
title: Code Sample Brace Bug
meta_title: Android Testing
meta_description: Apply our testing extension to your native Android application.
slug: deploy-android
tags: android testing, native
publish: true
ordinal: 2
---

# Android

Configure your Android app to be testable.

## Copy Extension

1. Open `/Telerik Mobile Testing/extensions/Android`.
2. Copy `MobileTestingExtension.jar`.
3. Open `/projectFolder/libs`.
4. Paste `MobileTestingExtension.jar`.

## Configure Testing Flavor

1. Open `/projectFolder/build.gradle`.
2. Add the following after `productFlavors` in the `android` object:

        android.applicationVariants.all { variant ->
        if (variant.flavorName == "testing") {
            variant.processResources.manifestFile = file('src/' + variant.flavorName + '/AndroidManifest.xml')
            variant.processManifest.enabled=false
            }
        }
            
    ![Build Variants](../images/build-variants.png) 

## Include Extension

1. Open `/projectFolder/build.gradle`.
2. Add the following line to the `dependencies` section:

        testingCompile files('libs/MobileTestingExtension.jar')

    ![Apply Testing Extension in Android Studio](../images/ext-android-studio.png)

## Create Subfolders

Create the following subfolders in the project:

* `/projectFolder/src/production`
* `/projectFolder/src/production/java`
* `/projectFolder/src/production/res`
* `/projectFolder/src/testing`
* `/projectFolder/src/testing/java`
* `/projectFolder/src/testing/res`

## Copy Android Manifest

1. Open `/projectFolder/src/main`.
2. Copy `AndroidManifest.xml`.
3. Open `/projectFolder/src/testing`.
4. Paste `AndroidManifest.xml`.

## Edit Android Manifest

1. Open `/projectFolder/src/testing/AndroidManifest.xml`.
2. Add the following top-level `instrumentation` element:

        <instrumentation
            android:targetPackage="your.app.package"
            android:name="com.telerik.testingextension.MobileTestingInstrumentation" />

    ![Instrumentation](../images/instrument.png)

3. Add the following `activity` element as a child of the `application` element:

        <activity
            android:name="com.telerik.testingextension.EntryPoint"
            android:theme="@android:style/Theme.NoDisplay">
        <intent-filter>
            <action android:name="com.telerik.testing.ACTION_AUTOMATE"/>
            <category android:name="android.intent.category.DEFAULT"/>
        </intent-filter>
        </activity>

    ![Activity](../images/activity.png)

4. Select **View > Tool Windows > Build Variants**.
5. Select the `testing` build variant and deploy it.

    ![Testing Build Variant](../images/testing-build-variant.png) ​