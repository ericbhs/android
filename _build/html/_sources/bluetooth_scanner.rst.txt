=================================
About BLE scanner project
=================================

.. contents:: :local:

Issue : app runs but doesn't detect any BLE devices 
====================================================

**Solution** : from https://www.youtube.com/watch?v=jqOQmtTBAio comments (*ranjithkumar pv* question)

* add the following lines in ``AndroidManifest.xml`` :

.. code-block:: xml

    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
    
* Configure the Android device to allow location on the app : Parameters > Applications > Applications Authorizations > Location > Enable it for the app "BLE Tutorial"

Issue : Android Studio build error
===================================

https://stackoverflow.com/questions/52790020/build-errors-after-android-studio-3-2-1-upgrade

Error like :

.. code-block:: none

    Could not find com.android.tools.build:aapt2:3.2.1-4818971**. Searched in the following locations:
        file:/C:/Users/sandeepk2/AppData/Local/Android/Sdk/extras/m2repository/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971.pom
        file:/C:/Users/sandeepk2/AppData/Local/Android/Sdk/extras/m2repository/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971-windows.jar
        file:/C:/Users/sandeepk2/AppData/Local/Android/Sdk/extras/google/m2repository/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971.pom
        file:/C:/Users/sandeepk2/AppData/Local/Android/Sdk/extras/google/m2repository/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971-windows.jar
        file:/C:/Users/sandeepk2/AppData/Local/Android/Sdk/extras/android/m2repository/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971.pom
        file:/C:/Users/sandeepk2/AppData/Local/Android/Sdk/extras/android/m2repository/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971-windows.jar
        https://jcenter.bintray.com/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971.pom
        https://jcenter.bintray.com/com/android/tools/build/aapt2/3.2.1-4818971/aapt2-3.2.1-4818971-windows.jar Required by:
        project :app
        
**Solution** : "Just add google() in root level in build.gradle"

.. code-block:: none

    buildscript {
        repositories {
            google() //  <--here
            jcenter()
        }
     }

    allprojects {
        repositories {
            google() //  <-- here
            jcenter()
        }
    }
