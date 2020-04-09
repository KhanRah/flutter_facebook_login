# facebooklogin
We can login in the application with facebook

## Getting Started

Flutter Facebook Login Steps

1.Creating Facebook Application & get APP name & App ID
2.Adding Facebook Package
3.Create a strings.xml file in your android folder
4.Configure your AndroidManifest.xml file


Goto facebook developers site and login with credentials.
Follow Steps MyApps-->create app-->enter display name--> dashboard --> facebook login setup --> quickstart --> android

Click Next for 1st two steps mentioned there

In 3rd step

add your package name in 1st text field eg. com.example.myapp
In second field add the above with .MainActivity eg com.example.myapp.MainActivity

Then save-->Usethis packagename--> Continue

Here we need to generate the hash key Follow the steps from there to generate haskkey based on the machine you have.
after generating hashkey paste below you see the text field and save--> continue

And go on next until the last step

Add a **strings.xml** file in android/app/src/main/res/values/strings.xml

and paste the below code in that file
_________________________________________________________________________________
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="app_name">myapp</string>

    <!-- Replace "000000000000" with your Facebook App ID here. -->
    <string name="facebook_app_id">000000000000</string>

    <!--
      Replace "000000000000" with your Facebook App ID here.
      **NOTE**: The scheme needs to start with `fb` and then your ID.
    -->
    <string name="fb_login_protocol_scheme">fb000000000000</string>
</resources>
____________________________________________________________________________________

Once you created the **strings.xml** file, you need to copy paste below code to **AndroidManifest.xml**
________________________________________________________________________________________________________
<meta-data android:name="com.facebook.sdk.ApplicationId" android:value="@string/facebook_app_id"/>
<activity android:name="com.facebook.FacebookActivity" android:configChanges=
    "keyboard|keyboardHidden|screenLayout|screenSize|orientation" android:label="@string/app_name" />

<activity android:name="com.facebook.CustomTabActivity" android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.BROWSABLE" />
        <data android:scheme="@string/fb_login_protocol_scheme" />
    </intent-filter>
</activity>
_________________________________________________________________________________________________________
Then follow the code in main.dart 

  



