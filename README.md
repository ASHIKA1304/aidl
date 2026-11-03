# Ex.No:2 Develop an android application to implement the AIDL server and client app. The server app hosts a Bound Service and contains the logic to return random colours to its client.The client app calls the service and changes the button's colour within the Main activity.



## AIM:

To Develop an android application to implement the AIDL server and client app. The server app hosts a Bound Service and contains the logic to return random colours to its client.
The client app calls the service and changes the button's colour within the Main activity using AIDL interface in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Griaffe )

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as CSAIDL and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file(client/server).

Step 7: Save and run the application.

## PROGRAM:
### lColorService.aidl
```
package com.example.colorserver;

interface IColorService {
    int getRandomColor();
}
```
## aidlserver app
### MainActivity.java
```java
package com.example.colorserver;

import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        TextView tv = findViewById(R.id.textView);
        tv.setText("Color Server Running");
    }
}
```
### ColorService.java
```java
package com.example.colorserver;

import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        TextView tv = findViewById(R.id.textView);
        tv.setText("Color Server Running");
    }
}
```
### Android Manifest.xml
```xml
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
        android:theme="@style/Theme.ColorServer">

        <!-- AIDL Bound Service -->
        <service
            android:name=".ColorService"
            android:exported="true">
            <intent-filter>
                <action android:name="com.example.colorserver.ColorService"/>
            </intent-filter>
        </service>

        <!-- Launcher Activity -->
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN"/>
                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>
        </activity>

    </application>

</manifest>
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
        android:theme="@style/Theme.ColorServer">

        <!-- AIDL Bound Service -->
        <service
            android:name=".ColorService"
            android:exported="true">
            <intent-filter>
                <action android:name="com.example.colorserver.ColorService"/>
            </intent-filter>
        </service>

        <!-- Launcher Activity -->
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN"/>
                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>
        </activity>

    </application>

</manifest>
```


### lColorService.aidl
```
package com.example.colorserver;

interface IColorService {
    int getRandomColor();
}
```
## OUTPUT

### aidlserver App
<img width="2875" height="1764" alt="image" src="https://github.com/user-attachments/assets/9f207bab-ae0b-447e-85d7-a8cba2e25173" />
### aidlclient app
<img width="2878" height="1760" alt="image" src="https://github.com/user-attachments/assets/09b2781e-fe01-410c-aada-b62c6eb41722" />

<img width="2879" height="1799" alt="image" src="https://github.com/user-attachments/assets/3e1f32b2-205a-4dbd-ba83-6cd6cf969434" />



## RESULT
Thus a Simple Android Application to create a AIDL interface and communicate the process between client and server using AIDL interface in Android Studio is developed and executed successfully.
