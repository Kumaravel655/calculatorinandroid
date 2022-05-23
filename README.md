
# Ex.No:7 Develop a simple calculator using android studio.

## AIM:

To develop a program to develop a simple calculator in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Artic Fox)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Display the calculator operation in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

/*
Program to print the text “calculator operation”.<br>
Developed by: Kumaravel.V<br>
Registeration Number : 212220230027
*/
## activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText2"
        android:layout_width="163dp"
        android:layout_height="39dp"
        android:layout_marginBottom="40dp"
        android:hint="Enter number 2"
        android:inputType="number"
        android:background="#2196F3"
        app:layout_constraintBottom_toTopOf="@+id/buttonsum"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.508"
        app:layout_constraintStart_toStartOf="parent" />

    <EditText
        android:id="@+id/editText1"
        android:layout_width="163dp"
        android:layout_height="39dp"
        android:layout_marginBottom="100dp"
        android:hint="Enter  number 1"
        android:inputType="number"
        android:background="#2196F3"
        app:layout_constraintBottom_toTopOf="@+id/buttonsum"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.508"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/buttonsum"
        android:layout_width="170dp"
        android:layout_height="59dp"
        android:text="Addition"
        android:theme="@android:style/Widget.Material.Button.Colored"
        app:layout_constraintBottom_toTopOf="@+id/buttonmul"
        app:layout_constraintEnd_toStartOf="@+id/buttonsub"
        app:layout_constraintHorizontal_bias="0.037"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.938" />

    <Button
        android:id="@+id/buttonsub"
        android:layout_width="155dp"
        android:layout_height="57dp"
        android:text="Subtraction"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.871"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.43" />

    <Button
        android:id="@+id/buttonmul"
        android:layout_width="166dp"
        android:layout_height="58dp"
        android:text="multiplication"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.024"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.543" />

    <TextView
        android:id="@+id/textView1"
        android:layout_width="166dp"
        android:layout_height="71dp"
        android:textAppearance="?android:attr/textAppearanceLarge"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.514"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText2"
        app:layout_constraintVertical_bias="0.505" />

    <Button
        android:id="@+id/buttondiv"
        android:layout_width="152dp"
        android:layout_height="59dp"
        android:layout_marginEnd="16dp"
        android:text="divition"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.721"
        app:layout_constraintStart_toEndOf="@+id/buttonmul"
        app:layout_constraintTop_toBottomOf="@+id/buttonsub"
        app:layout_constraintVertical_bias="0.058" />


</androidx.constraintlayout.widget.ConstraintLayout>
```
## activity_main.java

```
package com.example.calculator;



import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button btnsum = (Button) findViewById(R.id.buttonsum);
        Button btnsub = (Button) findViewById(R.id.buttonsub);
        Button btndiv = (Button) findViewById(R.id.buttondiv);
        Button btnmul = (Button) findViewById(R.id.buttonmul);
        final EditText etv = (EditText) findViewById(R.id.editText1);
        final EditText etv2 = (EditText) findViewById(R.id.editText2);
        final TextView result = (TextView) findViewById(R.id.textView1);

        btnsum.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                int sum = x + y;
                result.setText( x + " + " + y + " = " + sum);
            }
        });

        btnsub.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                int sub = x - y;
                result.setText( x + " - " + y + " = " + sub);
            }
        });

        btndiv.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                double div = (float)x /(float) y;
                result.setText(x + " / " + y + " = " + div);
            }
        });

        btnmul.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                int mul = x * y;
                result.setText(x + " * " + y + " = " + mul);
            }
        });


    }
}
```

##  OUTPUT
![Screenshot (18)](https://user-images.githubusercontent.com/75235334/169741111-8b2ae3b6-9a00-4746-913f-b7b504f436ea.png)

 ![Screenshot (22)](https://user-images.githubusercontent.com/75235334/169741277-1a7c7327-5418-4164-81ec-03e4e8980ee2.png)
![Screenshot (23)](https://user-images.githubusercontent.com/75235334/169741585-794af7a3-cd09-413b-882b-07d80c89d94f.png)

![Screenshot (24)](https://user-images.githubusercontent.com/75235334/169741629-6380e3cc-ef65-4f06-a068-a2e3e2433b3b.png)



## RESULT
Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.

