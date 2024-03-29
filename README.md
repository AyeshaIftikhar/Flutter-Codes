# Flutter Codes

[![Website Demo](https://img.shields.io/badge/Website-00FFFF?logo=google-chrome&logoColor=ffffff)](https://authentication-demo-a1eb6.web.app/) [![Documentation](https://img.shields.io/badge/Documentation-00FFFF?logo=Github&logoColor=FFFFFF)](https://https://ayeshaiftikhar.github.io//Flutter-Codes/) [![Detailed Documentation](https://img.shields.io/badge/Detailed_Documentation-00FFFF?logo=Github&logoColor=ffffff)](https://gist.github.com/AyeshaIftikhar/14dac69ca4c3b9d126c70d0dd02bea2f)  
## Quick Links 
[![Purpose](https://img.shields.io/badge/FLUTTER-Purpose_of_the_Repository-00FFFF)](#purpose-of-the-repository) 

[![Generic Packages](https://img.shields.io/badge/FLUTTER-Generic_Packages_being_Used-00FFFF)](#some-generic-flutter-packages) 

[![Splash Screen](https://img.shields.io/badge/FLUTTER-Animated_Splash_Screen-00FFFF)](#animated-splash-screen) 

[![Firebase](https://img.shields.io/badge/FLUTTER-Firebase-00FFFF)](#firebase) 

[![Cloud Firestore](https://img.shields.io/badge/FLUTTER-Cloud_Firestore-00FFFF)](#cloud-firestore) [![Collection](https://img.shields.io/badge/Cloud_Firestore-Collection-00FFFF)](#collection) [![Documents](https://img.shields.io/badge/Cloud_Firestore-Documents-00FFFF)](#documents) [![Setting up cloud firestore](https://img.shields.io/badge/Cloud_Firestore-Setup-00FFFF)](#setting-up-cloud-firestore) 

[![Firebase Storage](https://img.shields.io/badge/FLUTTER-Firebase_Storage-00FFFF)](#firebase-storage) [![Features](https://img.shields.io/badge/Firebase_Storage-Features-00FFFF)](#features-of-firebase-storage:) [![Configuration](https://img.shields.io/badge/Firebase_Storage-Configuration-00FFFF)](#configure-the-firebase-storage-in-your-project) 

[![Authentication](https://img.shields.io/badge/FLUTTER-Firebase_Authentication-00FFFF)](#authentication-modules) 

[![Google Authentication](https://img.shields.io/badge/Firebase-Google_Authentication-00FFFF)](#google-authentication)  [![Google Authentication Setup](https://img.shields.io/badge/Firebase-Google_Authentication_Setup-00FFFF)](#guidelines-for-google-authentication-setup) 

[![Facebook Authentication](https://img.shields.io/badge/Firebase-Facebook_Authentication-00FFFF)](#facebook-authentication) [![Facebook Developer Consoler Setup](https://img.shields.io/badge/Firebase-Facebook_Developer_Console_App_Setup-00FFFF)](#setup-application-on-facebook-developer-console) [![Enable Facebook Authentication](https://img.shields.io/badge/Firebase-Enable_Facebook_Authentication-00FFFF)](#enable-facebook-authentication)

[![One-to-One Chatting](https://img.shields.io/badge/Firebase-One_to_One_Chatting-00FFFF)]() [![One-to-One Calls](https://img.shields.io/badge/Firebase-One_to_One_Calls-00FFFF)]()


### Purpose of this Repository

I have made this repository for reusing the most commonly used code modules. As a developer, I know the headache of re-doing the same piece of code again and again and sometimes, you just forgot about one step and here you go, your code stops working with a long list of errors. So, here is the easiest solution I think of to make this repository and add all the working codes in it, to get it whenever they are needed.

#### Some Generic Flutter Packages
- I have used __Getx__ for _State Management_, you can read more about this dependency [here](https://pub.dev/packages/get). Getx just made the state management much easy as compared to other state management techniques __e.g.__ _Bloc and Provider_, etc. To use this package just add the following line in youe `pubspec.yaml` under `dependencies:`
```
dependencies:
    // other dependenices
    get: 
    // if we leave the version blank, the recent version of the dependency package will be added in our project.
```
- To add additional icons rather than built-in flutter icons I have used the __Font Awesone Flutter__ package, which provides neary 1500 additional Flutter icons. Read more about it [here](https://pub.dev/packages/font_awesome_flutter). To use this package just add the following line in youe `pubspec.yaml` under `dependencies:`
```
   font_awesome_flutter:
```
- All add Internet permission in `AndroidManifest.xml` to work properly on the physical device.
```
    <uses-permission android:name="android.permission.INTERNET" />
```


[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)

## Animated Splash Screen

[![Website Demo](https://img.shields.io/badge/Website-00FFFF?logo=google-chrome&logoColor=ffffff)](https://authentication-demo-a1eb6.web.app/#/)

Splash Screens made your applications look more professional and I have created a little module for animated splash screen. I have used the _Animated Splash Screen_ package for this and this package a little depend on the _Page Transition_ package. Read more about the animated splash screen package [here](https://pub.dev/packages/animated_splash_screen) and about the page transition package [here](https://pub.dev/packages/page_transition). Add these dependencies in `pubspec.yaml`: 
```
     animated_splash_screen:
     page_transition:
```
Create a new class named `AnimatedSplashScreen` add the following code in that class like this:
```dart
  return AnimatedSplashScreen(
      duration: 7,
      splash: "[n]https://i.imgur.com/p3i6j7o.png",
      nextScreen: Mainpage(),
      splashTransition: SplashTransition.fadeTransition,
      pageTransitionType: PageTransitionType.bottomToTop,
      backgroundColor: Colors.transparent,
    );
```
- __Note:__ if your are using a network image you have to follow this format: `"[n]YourURL.png"`.

Now just replace your `home:` attribute in your main function with `AnimatedSplashScreen()`
```dart
  void main(){
    runApp(
      MaterialApp(
        home: AnimatedSplashScreen(),
      ),
    );
  }
```

[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)

# Firebase
 Firebase gives you the tools to develop high-quality apps, grow your user base, and earn more money. Follow these instructions to get stated with firebase.

- Create a new firebase project at [Firebase Console](https://console.firebase.google.com/).

![Create Project](https://imgur.com/mQQOWwr.png)

- Add applications to your firebase project (all the required applications i.e. android, ios, webapp, etc.). Follow these instructions to add applications on firebase.

![Add Application](https://imgur.com/fX1zQcF.png)

- After adding apps and connecting your firebase project with your flutter project.

- For using __Firebase__ services, always add __Firebase Core__ package in your project. Read more about this package [here](https://pub.dev/packages/firebase_core).  To use this package just add the following line in youe `pubspec.yaml` under `dependencies:`
```
   firebase_core: 
```
- Add the following script in your *index.html* under <body></body> tag but before `main.dart.js` script, if you are using Firebase with Flutter Web.
```
    <script src="https://www.gstatic.com/firebasejs/7.20.0/firebase-app.js"></script>
```
__Note:__ connect your project to Firebase using the instruction available [here](https://firebase.google.com/docs/flutter/setup). And do not forget to make your `main` funtcion `Asyncronized`, and add `widgetsBinding.ensureinitialized` and `firebase.initializedapp()` before the `runApp()`. The flow of `main function` will look like this:
```dart
  void main() async{
     WidgetsFlutterBinding.ensureInitialized(); 
     await Firebase.initializeApp();
     runApp();
  }
```

[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)

## Cloud Firestore

Cloud firestore is used to store data of an application. Data is stored in _Collections and Documents__. 

#### Collection
A collection points out to a certain type of data class like collection of Pet. We can consider it as a class in object oriented language.

#### Documents
A collection consists of multiple documents which stores the data fields about an entity. Each document has a unique id in a collection which can be used to refer to the data included/saved in that document. In the same manner as an id of a sql database'table.

Just like an SQL database, we can perfrom different functions on data like
- Add 
- Update/Edit
- Delete
- Select 
- Querying

### Setting up Cloud Firestore

- First add _cloud firestore_ package in your `pubspec.yaml` under `dependencies`:
```
    cloud_firestore:
```
Read more about the working of this package [here](https://pub.dev/packages/cloud_firestore).

- In firebase project [console](https://console.firebase.google.com/). 
- Select _Cloud Firestore_ from left pane.

![Select Cloud Firestore](https://i.imgur.com/F7rxrxx.png)

- Click on _create database_ button to create your database.

![Create Database](https://i.imgur.com/EcIE8CC.png)

- Then update the rules for adding/retrieving data, then click next and enable it.

![Update Rules](https://i.imgur.com/RVR0Pff.png)

- Now you can create the collections and documents manually or integrate them with your software to add data.
For flutter web, add the following script under user <body></body> tag in `index.html`.

```
    <script src="https://www.gstatic.com/firebasejs/8.6.1/firebase-firestore.js"></script>
```

[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)

## Firebase Storage

Cloud Storage is designed to help you quickly and easily store and serve user-generated content without any server, such as photos and videos. 

#### Features of Firebase Storage:

- Firebase storage API lets you upload your users’ files to our cloud so they can be shared with anyone else!
- And if you have specific rules for sharing files with certain users, you can protect this content for users logged in with Firebase authentication.
- Security, of course, is the first concern. All transfers are performed over a secure connection.
- And, finally, storage, backed by Google cloud storage, scales to petabytes — that’s billions of photos — to meet your app’s needs. So you will never be out of space when you need it.

#### Configure the Firebase Storage in your project

- First, enable the Firebase storage in your project console [here](https://console.firebase.google.com/).

![Enable Firebase Storage](https://i.imgur.com/f75E7La.png)

It should look like this. Now, you can add the folders here or can upload images directly to be accessed later.

![Storage](https://i.imgur.com/CTy47sm.png)

- Now, we will setup the storage rules, it depends upon the scope of application. You can setup rules in the __Rules__ tab, initially the rules are setup that only authenticated users can read and write storage data. Below is the screenshot of default rules setup by firebase.

![Default Rules](https://i.imgur.com/kB9Is26.png)

- Add the _Firebase Storage_ package in your `pubspec.yaml` under the `dependencies'. 
```
    firebase_storage:
```
Read more about firebase storage package [here](https://pub.dev/packages/firebase_storage).

- Add this script in `index.html` under <body></body> tag.
```
    <script src="https://www.gstatic.com/firebasejs/8.6.1/firebase-storage.js"></script>
```
You do not need any additional steps to make this work, but however, some of the functionalities provided by this package does not work properly. So, I have used a different approach to make this work. 
    - I am creating a folder against each user named by their user id for easy management of data and I am adding a reference of your images in Cloud Firestore to retrieve the data because for me the function provided for retrieving the data from cloud storage does not really worked (If anyone know, how it will work. Feel free to share).
    - For removing the access of a picture from user side, I just update the firestore document of that particular user.
    
I have used _Image Picker_ package for getting image on Android and iOs and _File Picker_ package for Web. On Android and iOS, we need permissions for accessing gallery. 
    - Add External Storage Read & Write Permission for Android in `AnroidManifest.xml` file.
    `android> app> src> main> AndroidManifes.xml`
    ```
        <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
        <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
    ```
    - Add Photos permission in Info.plist for iOS.
    `ios> Runner> Info.plist`
    ```
        <key>NSPhotoLibraryUsageDescription</key>
	    <string>This app requires to save your images user gallery</string>
    ```

Add the image picker and file picker package along with permission handler package in `pubspec.yaml`.
```
    image_picker: 
```

We are using permission handler package because image picker package does not handle permissions by itself. Read more about image picker package [here](https://pub.dev/packages/image_picker). 

[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)

## Authentication Modules

We are using __Firebase Authentication__ in our project so we need to add __Firebase Auth__ package in `pubspec.yaml`. Read more about this [here](https://pub.dev/packages/firebase_auth).
```
    firebase_auth: 
```

- Add the following script in <body></body tag of `index.html` for flutter web.
    
```
    <script src="https://www.gstatic.com/firebasejs/7.20.0/firebase-auth.js"></script>
```

### Google Authentication
`Google Sign In using Firebase Authentication` 

[![Website Demo](https://img.shields.io/badge/Website-00FFFF?logo=google-chrome&logoColor=ffffff)](https://authentication-demo-a1eb6.web.app/#/)

Google Sign In is the most commonly used authentication method which is used by almost all the websites and other platforms. In this project, we are going to use google authentication which will also manage the auto signing in of a user by using __Shared Preferences__. Add _Google Sign In and Shared Preference_ packages into `pubspec.yaml` like this:
```
      google_sign_in:
      shared_preferences:
```
 Read more about google sign in [here](https://pub.dev/packages/google_sign_in) and about shared preferences [here](https://pub.dev/packages/shared_preferences).

### Guidelines for Google Authentication Setup

We will add authentication method (google) in our project.


#### Add Authentication Method
 - Go to your firebase console, Select Authentication from Left Pane. 
  
  ![Select Authentication](https://imgur.com/rvcPCVz.png)
  
   - Enable Google from _Sign-in Methods_. First, enable it then add the configuration email (try to add the same email which you have added in your project setting.) and the click save.
    
   ![Google](https://imgur.com/iB36R0T.png)
#### Additional Setup for Android
- Now, go to your _Google-services.json_ file in _root-directory > android > app_ and copy all __client id's__ one by one and add into your Authendication method under _Safelist client IDs from external projects (optional)_. It will enable google sign-in on android application.
    
   ![Safest Client Id's](https://imgur.com/IbHzanh.png)
   
It will generate the list of whitelist client id's to be used by the system.
  
### Additional Setup for Web Applications
Setting up google authentication for an website requires some additional steps, which we are going to discuss below:

- Go to [Google Cloud Platform](https://console.developers.google.com/) and create a new project there.
  
  ![creacte project](https://imgur.com/Kv3cTZP.png)
  
- Specify _Project Name_ and _Organization_ (if any) and click create. 
  
  ![project](https://imgur.com/em1m3MZ.png)
  
- We will generate web credentials, but for generating credentials we have to generate **OAuth Concent Screen** first.
  
  ![OAuth Consent Screen](https://imgur.com/Zom4edl.png)
  
   - Select the _User type_, the **external** is preferred most if you are going to publish your application outside your organization and then click create.

  ![Select User](https://imgur.com/fGreOn1.png)

  - Enter your application name, support email and logo of your application.

   ![App Name](https://imgur.com/FCUAuuB.png)

  - Enter your website domain in authorized domains.
  - Also, add links of your website home page, privacy policy and terms of services. 
    
   ![app domains](https://imgur.com/EmPYi2n.png)
   
  - Enter developer contact information and click _save & continue_.
  
  ![developers information](https://imgur.com/xRaeNty.png)
  
  - Add scopes (if you are using any.) otherwise, just click _save & continue_ at the end of the screen.
  ![scopes](https://imgur.com/VSTuRFL.png)
  
  - Add test user (if you there are any) otherwise, simply click _save & continue_.
  ![test users](https://imgur.com/6OJzJD6.png)
  
  - In summary tab, review the information you have provided so far and if you are saftisfied with the provided information then click _back to dashboard_ button at the end of the screen.

###### Note: The authorized domain and links of home page, privacy policy and terms of services are optional. It is up to you to add these links, you can also add these links later if you have not buy a domain of your project or generate the privacy policies. Adding privacy policy and terms of services shows the credibility of your project.


- After generating OAuth Consent Screen, now, we will generate credentials.
  - Select Credentials from the left pane.
  
  ![Credentials](https://imgur.com/Xngkrm3.png)
  
  - Click _create new credential_
  
  ![Create New Credential](https://imgur.com/QI0kk0Y.png)
  
  - Click _create new credential > OAuth Client ID_.
  
  ![OAuth Client ID](https://imgur.com/USWYklz.png)
  
  - Select _Web Application_ from the drop-down.
  
  ![Web Application](https://imgur.com/uJ0VAvh.png)
  
  - Add name of the _Auth Client_ and also add the links of your _localhost and the domain of your deployed website_ under __Authorized JavaScript Origins__.
  
  ![Name and JS Origin](https://imgur.com/5UA5nS6.png)
  
  - After it, click _save_ button. It will display a dialog box which includes _Your Client Id and Client Secert_.
  
  ![Client ID and Sceret](https://imgur.com/hMe3oYg.png)
  
  - Now, copy the client id and client secert and paste these in firebase: _Authentication>Sign0in Methods>Google>Web SDK Configurations_
  
  ![Web SDK Configurations](https://imgur.com/Hn7b3qV.png)
  
You are all set-up, just place the following two commands in your __index.html__.

  - Place this _Meta tag_ in <head></head> tag.
  
  ```
  <meta name="google-signin-client_id" content="yourclientid.apps.googleusercontent.com">
  ```
  
  - And place this script in <body></body> tag but before _main.dart.js_ script tag.
  
  ```
  <script src="https://apis.google.com/js/platform.js" async defer></script>
  ```

- To run the project on localhost while debugging use the following command.
  ```
  flutter run -d chrome --web-port 51396
  ```
  - And if you are using Microsoft edge or some other browser then use the command.
  ```
  flutter run -d web-browser-name --web-port 51396
  ```
  
  [![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)
  
## Facebook Authentication
Facebook authentication is also one of the common authentication methods used for uer sign up into an application by following minimum steps on user side, but for a developer you have to follow some steps to make it work properly in your application. The neccessary steps are mentioned below: 
- First, you have to setup an application on _Facebook Developers Console._ You can following the steps given in there documentation [here](https://developers.facebook.com/docs/).  
- Then, you need to  enable facebook auth provider in your [Firebase Console](https://console.firebase.google.com/u/0/project/_/authentication/providers) by setting up your facebook app id and secret.
- After that we will add the _[flutter_facebook_auth](https://pub.dev/packages/flutter_facebook_auth)_ package into `pubspec.yaml` file.
```
	flutter_facebook_auth: 
```

### Setup Application on Facebook Developer Console
- Create an application on facebook developer console if you do not have one before on this [link](https://developers.facebook.com/apps/)

![Add app](https://i.imgur.com/UYpMKqQ.png)

#### Android Setup
- Skip the step two (Download Facebook App) & three (Integrate Facebook SDK) in the documentation.
- Edit your resources by creating a `strings.xml` file in _**/android/app/src/main/src/values/strings.xml**_ and add the following configs there:
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="app_name">Flutter Codes</string>
    <string name="facebook_app_id">your_facebook_app_id</string>
    <string name="fb_login_protocol_scheme">fbyour_facebook_app_id</string>
</resources>
```
- Add the following permission in `AndroidManifest.xml`
```
<uses-permission android:name="android.permission.INTERNET"/>

```
- Now add the following config in you `AndroidManifest.xml` file.
```
<!-- Facebook Sign in -->
<meta-data android:name="com.facebook.sdk.ApplicationId" android:value="@string/facebook_app_id" />		
<activity 
	  android:name="com.facebook.FacebookActivity" 
	  android:configChanges="keyboard|keyboardHidden|screenLayout|screenSize|orientation" 
	  android:label="@string/app_name" 
/>
<activity android:name="com.facebook.CustomTabActivity" android:exported="true">
	<intent-filter>
		<action android:name="android.intent.action.VIEW" />
		<category android:name="android.intent.category.DEFAULT" />
		<category android:name="android.intent.category.BROWSABLE" />
		<data android:scheme="@string/fb_login_protocol_scheme" />
	</intent-filter>	
</activity>
<!-- For fetching photo or video -->
<provider 
	 android:authorities="com.facebook.app.FacebookContentProvider945416459634045"
         android:name="com.facebook.FacebookContentProvider"
         android:exported="true"
/>
```
- Now associalte your package name and default class of your app

![Package Name](https://i.imgur.com/tnXZm2c.png)
 
- Now provide development and release key hashes. You need to follow the instructions mentioned here to get the key hashes [https://developers.facebook.com/docs/facebook-login/android?locale=en_US#6--provide-the-development-and-release-key-hashes-for-your-app](https://developers.facebook.com/docs/facebook-login/android?locale=en_US#6--provide-the-development-and-release-key-hashes-for-your-app)

![key hashes](https://i.imgur.com/viRthgD.png)

**Note:** if you find it difficult to get the hash  key by following the instructions. You can convert the SHA1 into your hash key on this [Hex to Base64 Converter](http://tomeko.net/online_tools/hex_to_base64.php). You just need to put your SHA1 key and it will generate the hash key. 

![hash key converter](https://i.imgur.com/4Rb73fX.png)


#### Website Setup
- You need to add the facebook javascript sdk into your `index.html` file.
```
<!-- ADD THIS SCRIPT -->
<script async defer crossorigin="anonymous" src="https://connect.facebook.net/en_US/sdk.js"></script>
```
- In `main.dart`, add the following code but before `runapp()`
```dart
if (kIsWeb) {
    // initialiaze the facebook javascript SDK
    FacebookAuth.i.webInitialize(
      appId: "YOUR APP_ID",
      cookie: true,
      xfbml: true,
      version: "v1.0",
    );
  }
```
- Apart from this, you need to add your website url too. 

	![Website URL](https://i.imgur.com/cCWl0rc.png)

- Also you need to add all the domains and subdomain related to your application. To add these go to your app's** _settings>basic_**

	![App Domains](https://i.imgur.com/Tb3aEpZ.png)

_**Note:**_ You need to add domain names without `http/https`. And you can also add a logo of your application and the privacy policy and terms of services.

[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes) 

### Enable Facebook Authentication 
- In your [Firebase Console](https://console.firebase.google.com/), go to _**Authentications>Sign-in Methods**_ and enable facebook sign in by providing the Facebook Application ID and Secret Key and it will provide a `OAuth Redirect URI`.
	- On the other note, you will find your facebook app id and secret in your app's setting on the mentioned link [https://developers.facebook.com/apps/your_app_id/settings/basic/](https://developers.facebook.com/apps/your_app_id/settings/basic/)

	![id and secret](https://i.imgur.com/5Fg1xda.png)
	
	- Add these credentials in your sign-in method to enable it.
	
	![Enable Facebook Sign in](https://imgur.com/lFjqTFg.png) 

- After getting the _OAuth Redirect URI_, we will add that URI into our application. By following the path at here [https://developers.facebook.com/apps/ypur_app_id/fb-login/settings/](https://developers.facebook.com/apps/your_app_id/fb-login/settings/)

	![oauth redirect uri](https://i.imgur.com/lIUQSt5.png)
 
[![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes) 
 
### Application Screenshots
 
  ![Splash Screen](https://i.imgur.com/ysNRzZC.png)
  ![Login Screen](https://i.imgur.com/i8hgGKl.png) ![User Profile](https://i.imgur.com/piNO4VC.png)
  ![File Picker](https://i.imgur.com/nv18Chg.png) 
 
  
  
  [![TOP](https://img.shields.io/badge/Goto-Top-000000)](#flutter-codes)
  
 Check the web application [here](https://authentication-demo-a1eb6.web.app/#/).
 
 You are all set, just clone the repository and use the code in your project.
 
 Happy Coding 😊
  
  

      
 
 





## Let's Connect
[![Ayesha Iftikhar](https://img.shields.io/badge/Ayesha_Iftikhar-000000?logo=opsgenie&logoColor=ffffff)](https://ayeshaiftikhar.github.io) [![Github](https://img.shields.io/badge/Github-Follow-211F1F?logo=GitHub&logoColor=ffffff)](https://github.com/AyeshaIftikhar/) [![Linkedin](https://img.shields.io/badge/Linkedin-Connect-0077B5?logo=Linkedin&logoColor=ffffff)](https://www.linkedin.com/in/seayeshaiftikhar/)  [![Facebook](https://img.shields.io/badge/Facebook-1877F2?logo=Facebook&logoColor=ffffff)](https://www.facebook.com/seayeshaiftikhar/) [![Twitter](https://img.shields.io/badge/Twitter-Follow-08A0E9?logo=Twitter&logoColor=ffffff)](https://www.twitter.com/seaishaiftikhar/) [![Instagram](https://img.shields.io/badge/Instagram-Follow-DD2A7B?logo=Instagram&logoColor=ffffff)](https://www.instagram.com/seayeshaiftikhar/) [![Youtube](https://img.shields.io/badge/Youtube-Subscribe-FF0000?logo=Youtube&logoColor=ffffff)](https://www.youtube.com/channel/UCUI0fN6xPUT3SfGLfh8B9Lg) [![Medium](https://img.shields.io/badge/Medium-Follow-0077B5?logo=Medium&logoColor=ffffff)](https://www.medium.com/@seayeshaiftikhar) [![StackOverflow](https://img.shields.io/badge/Stackoverflow-211F1F?logo=stackoverflow&logoColor=ffffff)](https://stackoverflow.com/users/9611960/ayesha-iftikhar) [![Gmail](https://img.shields.io/badge/Gmail-D44638?logo=gmail&logoColor=ffffff)](mailto:seayeshaiftikharl@gmail.com) [![Messenger](https://img.shields.io/badge/Chat-1877F2?logo=Messenger&logoColor=ffffff)](https://m.me/seayeshaiftikhar/) [![WhatsApp](https://img.shields.io/badge/Chat-25D366?logo=WhatsApp&logoColor=ffffff)](https://wa.me/923137128036?text=%23Github) [![RPubs](https://img.shields.io/badge/Rpubs-CD5C5C?logo=R&logoColor=ffffff)](https://rpubs.com/seAyeshaIftikhar)


