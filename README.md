# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
```
Start the application.

Create an EditText to enter the website URL and a Navigate button.

Read the URL entered by the user when the Navigate button is clicked.

Check whether the URL starts with http:// or https://; if not, add http:// to the beginning.

Create an Implicit Intent using Intent.ACTION_VIEW and pass the URL as a Uri.

Launch the intent using startActivity() to open the URL in the default web browser.

Display the requested webpage (e.g., www.gmail.com) and stop the application.

```
## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: Marxin Lijo M
Registeration Number : 212223240085
*/
```


Main activity.java

```

package com.example.exp_02;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    EditText editTextURL;
    Button btnOpen;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextURL = findViewById(R.id.editTextURL);
        btnOpen = findViewById(R.id.btnOpen);

        btnOpen.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String url = editTextURL.getText().toString().trim();

                // If URL doesn’t start with http/https, add it
                if (!url.startsWith("http://") && !url.startsWith("https://")) {
                    url = "http://" + url;
                }

                // Implicit Intent to open URL
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            }
        });
    }
}


```
Android manifest.xml
```

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.EXP02">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

```


## OUTPUT
<img width="1536" height="815" alt="Screenshot 2026-07-27 141333" src="https://github.com/user-attachments/assets/3c706506-4d4a-4929-81fd-ba54a51a554d" />
<img width="1536" height="812" alt="Screenshot 2026-07-27 141500" src="https://github.com/user-attachments/assets/82270367-67b6-452f-afb9-77405251ca67" />





## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


