**GButtons**
---

You want to add a Google Sign-In button to your Android application. But you want to change the text on the Google Sign-In button or provide custom localization? You would think setting `android:text` on the `com.google.android.gms.common.SignInButton` in your layout file would do the trick. However it turns out that that attribute is not available for `SignInButton`. 

**Solution**
---

This library helps you add text to Google Sign-In Button easily using standard `android:text` attribute. It also allows you to set the button theme to dark or light using `app:isDarkTheme="true"` attribute. It does so following Google's guidelines to create sign-in button.

Light Theme (White)        |  Dark Theme (Blue)
:-------------------------:|:-------------------------:
![Google Sign-In Light](images/GoogleSignInLight.png)  |  ![Google Sign-In Dark](images/GoogleSignUpDark.png)


**Usage**
---

One-step install

Add it in your root build.gradle at the end of repositories:

```allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

Step 2. Add the dependency

Add the following to your `app` module level `build.gradle` file:

```gradle
dependencies {
    implementation 'com.github.TutorialsAndroid:gbutton:v1.0.19'
}
```

In your XML Layout, have the following:

```xml
<RelativeLayout
    ...
    xmlns:app="http://schemas.android.com/apk/res-auto">

    <com.developer.gbuttons
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="@string/google_sign_up"
        app:isDarkTheme="true" />
</RelativeLayout>
```


**Options**
---

- `app:isDarkTheme="{Boolean}"` : To switch between blue theme and gray white for the button. The library handles changing of text color and background color. It also handles the change of color on button press or button clicks.
- `android:text="{string}"`: As usual to set the text on the button.

**Google's Suggestion**
---

From documentation, Google suggests creating a custom button as mentioned on [Customizing the Sign-In Button](https://developers.google.com/identity/sign-in/android/custom-button). Then it suggests using the branding guidelines as mentioned at [Sign-In Branding Guidelines](https://developers.google.com/identity/branding-guidelines#sign-in-button). It includes using custom icons and images int he button, setting text size to specifics, paddings and other do's and don'ts for the logo. 


Doing as per Google's suggestion involves some custom work. This small 3.93 KB library does that for you. Please feel free to make pull requests to improve the library. I wanted to create a re-usable solution when I came across this problem while implementing the Sign-In button. Just wanted to share with everyone.


**License**
```
Copyright 2019 GButton

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

 http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

