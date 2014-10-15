Print
=====

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Print-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1016)

A lightweight Android library for use iconic fonts.

![image](https://raw.githubusercontent.com/johnkil/Print/master/art/print.jpg)

<a href="https://play.google.com/store/apps/details?id=com.github.johnkil.print.sample">
  <img alt="Get it on Google Play"
       src="http://www.android.com/images/brand/get_it_on_play_logo_small.png" />
</a>

Download
--------

Gradle:

```groovy
compile 'com.github.johnkil.print:print:1.1.0'
```

Maven:

```xml
<dependency>
    <groupId>com.github.johnkil.print</groupId>
    <artifactId>print</artifactId>
    <version>1.1.0</version>
</dependency>
```

Usage
-----

First, you need to initialize the iconic font in [Application.onCreate()][1] method.

```java
public class MyApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();                
        Print.initFont(getAssets(), "fonts/iconic-font.ttf");
    }

}
```

#### PrintView

Use `PrintView` as single icon in your layout.

```xml
<com.github.johnkil.print.widget.PrintView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        print:iconColor="@color/icon_color"
        print:iconSize="@dimen/icon_size"
        print:iconText="@string/ic_android"
        android:contentDescription="@string/ic_android_description"/>
```

#### PrintButton

Use `PrintButton` to create a button with an icon.

```xml
<com.github.johnkil.print.widget.PrintButton
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        print:iconColor="@color/icon_color"
        print:iconSize="@dimen/icon_size"
        print:iconText="@string/ic_android"
        android:contentDescription="@string/ic_android_description"/>
```

#### PrintDrawable

If you need an icon in `ImageView` or in `ActionBar`, then you should use `PrintDrawable`.

```java
ImageView imageView = (ImageView) findViewById(R.id.image);
// Set an icon in the ImageView
imageView.setImageDrawable(new PrintDrawable()
        .iconText(getResources().getString(R.string.ic_info))
        .iconColor(getResources().getColor(R.color.icon_color))
        .iconSize(getResources().getDimensionPixelSize(R.dimen.icon_size)));
```

```java
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.main, menu);
    // Set an icon in the ActionBar
    menu.findItem(R.id.action_info).setIcon(
            new PrintDrawable()
                    .iconText(getResources().getString(R.string.ic_info))
                    .iconColor(getResources().getColor(R.color.ab_icon_color))
                    .iconSize(getResources().getDimensionPixelSize(R.dimen.ab_icon_size))
    );
    return true;
}
```

Links
-----

* [Android-Icon-Fonts][2] - Material and Holo iconic fonts.


License
-------

    Copyright 2014 Evgeny Shishkin
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
       http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
    

[1]: http://developer.android.com/reference/android/app/Application.html#onCreate%28%29
[2]: https://github.com/johnkil/Android-Icon-Fonts