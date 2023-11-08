# MAD-workshop5

## Design an application view to display the 'n' number of images using GridView Control/Widget in android studio.

## AIM:
To design an application view to display the 'n' number of images using GridView Control/Widget in android studio.
```
/*
Submitted by: ILAYARAJA M
Register number: 212221040057
*/
```
## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/gridView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <GridView
        android:id="@+id/simpleGridView"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="20dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="20dp"
        android:layout_marginBottom="20dp"
        android:numColumns="5"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:horizontalSpacing="10dp"
        android:verticalSpacing="10dp"
        app:layout_constraintVertical_bias="1.0" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

## grid_item.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="200dp"
    android:layout_height="300dp"
    android:padding="3dp"
    android:layout_margin="5dp">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_weight="1"
        android:text="TextView" />
</LinearLayout>
```

## MainActivity.java:
```
package com.example.gridcontrol;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.GridView;
import android.widget.TextView;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
    GridView gridView;
    TextView textView;
    String[] carBrands = {
            "Ferrari",
            "McLaren",
            "Jaguar",
            "Skoda",
            "Suzuki",
            "Hyundai",
            "Toyota",
            "Renault",
            "Mercedes",
            "BMW",
            "Ford",
            "Honda",
            "Chevrolet",
            "Volkswagon",
    };
    @SuppressLint("MissingInflatedId")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        gridView = (GridView)findViewById(R.id.simpleGridView);
        textView = (TextView)findViewById(R.id.textView);
        final ArrayAdapter adapter = new ArrayAdapter(this, R.layout.grid_item,
                R.id.textView, carBrands);
        gridView.setAdapter(adapter);
        gridView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> adapterView, View view, int position, long
                    l) {
                String value = "I Love " + adapter.getItem(position);
                Toast.makeText(getApplicationContext(), value, Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

## OUTPUT:
![Screenshot (358)](https://github.com/ashmistalin/MAD--Workshop5/assets/103128410/f1f727aa-47f4-4634-87d6-4c2b8f3e0179)
![Screenshot (359)](https://github.com/ashmistalin/MAD--Workshop5/assets/103128410/55acfc53-8fba-41cd-9735-6375f007f0a5)


## RESULT:
Thus an application view to display the 'n' number of images using GridView Control/Widget in android studio is desgined.
