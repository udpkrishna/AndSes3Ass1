# AndSes3Ass1
Andriod Session2 Assignment1
Main Activity.java
package me.rk.andses3ass1;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.support.v7.widget.SwitchCompat;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity implements View.OnClickListener{

    private Button hidebutton;
    private Button showbutton;
    private ImageView image1;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        hidebutton= (Button) findViewById(R.id.buttonhide);
        hidebutton.setOnClickListener(this);

        showbutton=(Button) findViewById(R.id.buttonshow);
        showbutton.setOnClickListener(this);

        image1=(ImageView) findViewById(R.id.imageView);
    }

    @Override
    public void onClick(View v) {
        int id=v.getId();

        switch(id){
            case R.id.buttonhide:
                image1.setVisibility(View.INVISIBLE);
                showbutton.setVisibility(View.VISIBLE);
                hidebutton.setVisibility(View.GONE);
                break;

            case R.id.buttonshow:
                image1.setVisibility(View.VISIBLE);
                showbutton.setVisibility(View.GONE);
                hidebutton.setVisibility(View.VISIBLE);
                break;
        }
    }
}


Activity Main. XML
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#000000"
    tools:context="me.rk.andses3ass1.MainActivity">

    <TextView
        android:text="Hello World!"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />


    <Button
        android:id="@+id/buttonhide"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hide"
        android:background="#06d8db"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:layout_alignStart="@+id/buttonshow" />

    <Button
        android:id="@+id/buttonshow"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Show"
        android:background="#06d8db"
        android:layout_centerHorizontal="true"
        android:layout_alignParentBottom="true"
        android:visibility="gone"/>

    <ImageView

        android:id="@+id/imageView"
        android:maxHeight="100dp"
        android:layout_centerHorizontal="true"
        android:src="@mipmap/image1"
        android:layout_height="match_parent"
        android:layout_width="match_parent"
        android:layout_above="@+id/buttonshow" />


</RelativeLayout>
