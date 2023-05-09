
# Rapport

I chose to use Calligraphy library because it is one of the most popular custom font libraries 
available. With this library, we can declare a single font across the whole application 
or define fonts individually to a text.

First I added the dependency in app-module build.gradle file and sync it.
```
implementation 'uk.co.chrisjenx:calligraphy:2.3.0'
```

After that I created an assets folder and inserted Red Velvet font.
I initialize the library and set default font in the Application class.

```
public class App extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        CalligraphyConfig.initDefault(new CalligraphyConfig.Builder()
                .setDefaultFontPath("red-velvet.ttf")
                .setFontAttrId(R.attr.fontPath)
                .build()
        );
    }
}
```

I override the attachBaseContext method in each Main activity:

```
@Override
protected void attachBaseContext(Context newBase) {
    super.attachBaseContext(CalligraphyContextWrapper.wrap(newBase));
}
```

After that I added TextViews to see if the library works:

```
 <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Here was Violeta!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.615"/>

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="This text is in Red Velvet"
        app:layout_constraintBottom_toTopOf="@+id/textView2"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
```

However I am having some issues with compileSdkVersion . I changed the values from 30 to 33
and from 16 to 24, but it still does not work.
```
compileSdkVersion 33
buildToolsVersion "30.0.3"

    defaultConfig {
        applicationId "com.example.externallibraries"
        minSdkVersion 24
        targetSdkVersion 33     
```
Bilder läggs i samma mapp som markdown-filen.

