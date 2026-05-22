# Ex.No: 6 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Design xml files for all operations such as blink, rotate, move, slide, zoom, fade.

Step 6: Display the button operations in MainActivity file.

Step 7: Save and run the application


## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Prideesh M
Registeration Number : 212223040154
*/
```
### ACTIVITY_MAIN.XML:
```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/heading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:text="@string/heading_text"
        android:textColor="#000000"
        android:textSize="22sp"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="219dp"
        android:layout_height="263dp"
        app:layout_constraintBottom_toTopOf="@+id/BTNblink"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/heading"
        app:layout_constraintVertical_bias="0.2"
        app:srcCompat="@drawable/dog" />

    <!-- First Row -->
    <Button
        android:id="@+id/BTNblink"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="4dp"
        android:backgroundTint="#3F51B5"
        android:text="Blink"
        app:layout_constraintBottom_toTopOf="@+id/BTNmove"
        app:layout_constraintEnd_toStartOf="@+id/BTNrotate"
        app:layout_constraintHorizontal_chainStyle="spread"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_chainStyle="packed" />

    <Button
        android:id="@+id/BTNrotate"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="4dp"
        android:backgroundTint="#3F51B5"
        android:text="Rotate"
        app:layout_constraintBottom_toBottomOf="@+id/BTNblink"
        app:layout_constraintEnd_toStartOf="@+id/BTNfade"
        app:layout_constraintStart_toEndOf="@+id/BTNblink"
        app:layout_constraintTop_toTopOf="@+id/BTNblink" />

    <Button
        android:id="@+id/BTNfade"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="8dp"
        android:backgroundTint="#3F51B5"
        android:text="Fade"
        app:layout_constraintBottom_toBottomOf="@+id/BTNblink"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/BTNrotate"
        app:layout_constraintTop_toTopOf="@+id/BTNblink" />

    <!-- Second Row -->
    <Button
        android:id="@+id/BTNmove"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="4dp"
        android:backgroundTint="#3F51B5"
        android:text="Move"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toStartOf="@+id/BTNslide"
        app:layout_constraintHorizontal_chainStyle="spread"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/BTNblink" />

    <Button
        android:id="@+id/BTNslide"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="4dp"
        android:backgroundTint="#3F51B5"
        android:text="Slide"
        app:layout_constraintBottom_toBottomOf="@+id/BTNmove"
        app:layout_constraintEnd_toStartOf="@+id/BTNzoom"
        app:layout_constraintStart_toEndOf="@+id/BTNmove"
        app:layout_constraintTop_toTopOf="@+id/BTNmove" />

    <Button
        android:id="@+id/BTNzoom"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="8dp"
        android:backgroundTint="#3F51B5"
        android:text="Zoom"
        app:layout_constraintBottom_toBottomOf="@+id/BTNmove"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/BTNslide"
        app:layout_constraintTop_toTopOf="@+id/BTNmove" />

    <!-- Stop Button -->
    <Button
        android:id="@+id/BTNstop"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:layout_marginBottom="32dp"
        android:backgroundTint="#F44336"
        android:paddingStart="32dp"
        android:paddingEnd="32dp"
        android:text="Stop Animation"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/BTNmove" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### MAIN_ACTIVITY.JAVA:
```java
package com.example.muiex_06;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
    ImageView imageView;
    Button blinkBTN, rotateBTN, fadeBTN, moveBTN, slideBTN, zoomBTN, stopBTN;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);
        blinkBTN = findViewById(R.id.BTNblink);
        rotateBTN = findViewById(R.id.BTNrotate);
        fadeBTN = findViewById(R.id.BTNfade);
        moveBTN = findViewById(R.id.BTNmove);
        slideBTN = findViewById(R.id.BTNslide);
        zoomBTN = findViewById(R.id.BTNzoom);
        stopBTN = findViewById(R.id.BTNstop);

        blinkBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add blink animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.blink);
                imageView.startAnimation(animation);
            }
        });

        rotateBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add rotate animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.rotate);
                imageView.startAnimation(animation);
            }
        });

        fadeBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add fade animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.fade);
                imageView.startAnimation(animation);
            }
        });

        moveBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add move animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.move);
                imageView.startAnimation(animation);
            }
        });

        slideBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add slide animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.slide);
                imageView.startAnimation(animation);
            }
        });

        zoomBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add zoom animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.zoom);
                imageView.startAnimation(animation);
            }
        });

        stopBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To stop the animation going on imageview
                imageView.clearAnimation();
            }
        });
    }
}
```

### BLINK.XML
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0" android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500" android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>
```
### ROTATE.XML
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <rotate
        android:duration="6000"
        android:fromDegrees="0"
        android:pivotX="50%"
        android:pivotY="50%"
        android:toDegrees="360" />
    <rotate
        android:duration="6000"
        android:fromDegrees="360"
        android:pivotX="50%"
        android:pivotY="50%"
        android:startOffset="5000"
        android:toDegrees="0" />
</set>
```
### FADE.XML
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <!-- duration is the time for which animation will work-->
    <alpha
        android:duration="1000"
        android:fromAlpha="0"
        android:toAlpha="1" />
    <alpha
        android:duration="1000"
        android:fromAlpha="1"
        android:startOffset="2000"
        android:toAlpha="0" />
</set>
```
### MOVE.XML
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:fromXDelta="0%p"
        android:toXDelta="75%p"
        android:duration="700" />
</set>
```
### SLIDE.XML
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale android:duration="500"
        android:fromXScale="1.0" android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>
```
### ZOOM.XML
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:fromXScale="0.5" android:toXScale="3.0"
        android:fromYScale="0.5" android:toYScale="3.0"
        android:duration="1000" android:pivotX="25%"
        android:pivotY="25%" >
    </scale>
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:startOffset="1000" android:fromXScale="3.0"
        android:toXScale="0.5" android:fromYScale="3.0"
        android:toYScale="0.5" android:duration="1000"
        android:pivotX="25%" android:pivotY="25%" >
    </scale>
</set>
```
## OUTPUT
<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/2c0d2776-989e-4716-9e11-e8724ab34a13" />
<img width="1913" height="1079" alt="image" src="https://github.com/user-attachments/assets/0954aee3-4aa3-45f3-979a-3f74c4f1bd50" />
<img width="1914" height="1079" alt="image" src="https://github.com/user-attachments/assets/75c6ba49-5661-48c9-a087-c92eca9d5271" />
<img width="1919" height="1078" alt="image" src="https://github.com/user-attachments/assets/6f4d2008-9ebd-425d-941a-20201ef0aad5" />
<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/92c26d59-abe3-44d8-a551-d388de7a50d5" />
<img width="1913" height="1077" alt="image" src="https://github.com/user-attachments/assets/c649afaa-0b14-429b-8664-5ba1fbce6fd0" />
<img width="1916" height="1074" alt="image" src="https://github.com/user-attachments/assets/b3cfa9e5-5718-48da-8b96-b5a08d25e3d7" />




## RESULT
Thus a Simple Android Application to add animations: Move,blink,fade,clockwise,zoom,slide operations using Android Studio is developed and executed successfully.
