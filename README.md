# ProjectFibonacci

Nama           : Nadya Khairunnisa

NIM            : 312210133

Kelas          : TI.22.A.1

Mata Kuliah    : Pemrograman Mobile 1

Dosen Pengampu : Donny Maulana, S.Kom., M.Kom

# Tugas Pertemuan 6

![gambar tugas](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/49aaf952-758f-404e-a68e-7da72c9b66b1)

# Langkah-Langkah

1. Membuat project baru terlebih dahulu dengan nama project "tugasenam"

2. Kemudian pada layout activity_main ditambahkan 3 "button" dan 1 "textview" seperti berikut

![layout fibonacci](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/2277686e-cf2b-4350-8e7d-add0b550b19b)

3. Untuk button yang pertama berfungsi sebagai tombol "Toast" yang nantinya ketika ditekan akan muncul sebuah toast message yaitu "Bilangan Fibonacci". Button yang kedua, berfungsi sebagai tombol “count” yang nantinya ketika tombol ditekan akan menghitung bilangan fibonaccinya. Dan yang terakhir Textview, yang berfungsi untuk menampilkan angka atau bilangan fibonaccinya yang tepat berada di tengah.

4. Kemudian kita masukkan untuk codingan didalam activity_fibonacci seperti berikut

 * activity_fibonacci.xml
  
        <?xml version="1.0" encoding="utf-8"?>
        <androidx.constraintlayout.widget.ConstraintLayout
            xmlns:android="http://schemas.android.com/apk/res/android"
            xmlns:app="http://schemas.android.com/apk/res-auto"
            xmlns:tools="http://schemas.android.com/tools"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            tools:context=".MainActivity">
    
        <Button
            android:id="@+id/button_limit"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_marginEnd="8dp"
            android:layout_marginStart="8dp"
            android:layout_marginTop="8dp"
            android:background="@color/colorPrimary"
            android:onClick="setLimit"
            android:textColor="@android:color/white"
            android:text="@string/enter_fibonacci_limit"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            tools:ignore="UsingOnClickInXml,VisualLintButtonSize"/>
    
    
        <Button
            android:id="@+id/button_count"
            android:layout_width="190dp"
            android:layout_height="48dp"
            android:layout_marginStart="8dp"
            android:layout_marginEnd="8dp"
            android:layout_marginBottom="8dp"
            android:background="@color/colorPrimary"
            android:onClick="countUp"
            android:text="@string/button_label_count"
            android:textColor="@android:color/white"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintHorizontal_bias="0.0"
            app:layout_constraintStart_toStartOf="parent"
            tools:ignore="UsingOnClickInXml,VisualLintButtonSize" />
    
        <Button
            android:id="@+id/button_finish"
            android:layout_width="190dp"
            android:layout_height="48dp"
            android:layout_marginStart="8dp"
            android:layout_marginEnd="8dp"
            android:layout_marginBottom="8dp"
            android:background="@color/colorPrimary"
            android:onClick="back1"
            android:text="@string/button_label_finish"
            android:textColor="@android:color/white"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintHorizontal_bias="1.0"
            app:layout_constraintStart_toStartOf="parent"
            tools:ignore="UsingOnClickInXml" />
    
        <TextView
            android:id="@+id/show_count"
            android:layout_width="0dp"
            android:layout_height="0dp"
            android:layout_marginStart="8dp"
            android:layout_marginTop="8dp"
            android:layout_marginEnd="8dp"
            android:layout_marginBottom="8dp"
            android:background="#FFFF00"
            android:gravity="center_vertical"
            android:text="@string/count_initial_value"
            android:textAlignment="center"
            android:textColor="@color/colorPrimary"
            android:textSize="160sp"
            android:textStyle="bold"
            app:layout_constraintBottom_toTopOf="@id/button_count"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@id/button_limit"
            tools:ignore="RtlCompat" />
    
        </androidx.constraintlayout.widget.ConstraintLayout>
   
  * strings.xml
 
        <resources>
          <string name="app_name">Tugasenam</string>
          <string name="button_label_count">Count</string>
          <string name="count_initial_value"> </string>
          <string name="button_label_finish">Reset</string>
          <string name="enter_fibonacci_limit">Masukan Limit Angka</string>
        </resources>
    
* colors.xml
   
            <?xml version="1.0" encoding="utf-8"?>
            <resources>
                <color name="black">#FF000000</color>
                <color name="white">#FFFFFFFF</color>
                <color name="colorPrimary">#3F5185</color>
                <color name="colorPrimaryDark">#303F9F</color>
                <color name="colorAccent">#FF4081</color>
            </resources>


  # Tampilan Design

  ![tampilan design](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/ec02ff54-1c1c-4d25-b477-be9a82311e10)

  # MainActivity.java

  Pada MainActivity.java berisi semua codingan untuk fungsi-fungsinya. Seperti, fungsi untuk 
  tombol-tombol dan rumus bilangan fibonaccinya.

          package com.tugasenam;
          
          import android.app.AlertDialog;
          import android.content.DialogInterface;
          import android.os.Bundle;
          import android.view.View;
          import android.widget.EditText;
          import android.widget.TextView;
          import androidx.appcompat.app.AppCompatActivity;
          
          public class MainActivity extends AppCompatActivity {
              private TextView showCount;
              private int count = 1;
              private long fibNMinus1 = 1;
              private long fibNMinus2 = 0;
              private int limit = -1; // Inisialisasi limit dengan nilai default
          
              @Override
              protected void onCreate(Bundle savedInstanceState) {
                  super.onCreate(savedInstanceState);
                  setContentView(R.layout.activity_fibonacci);
          
                  showCount = findViewById(R.id.show_count);
              }
          
              public void countUp(View view) {
                  if (count == 0) {
                      showCount.setText("0");
                  } else if (count == 1) {
                      showCount.setText("1");
                  } else {
                      if (limit != -1 && count > limit) {
                          // Jika count melebihi limit, atur ulang perhitungan
                          count = 0;
                          fibNMinus1 = 1;
                          fibNMinus2 = 0;
                          showCount.setText(getString(R.string.count_initial_value));
                      } else {
                          long fibCurrent = fibNMinus1 + fibNMinus2;
                          fibNMinus2 = fibNMinus1;
                          fibNMinus1 = fibCurrent;
                          showCount.setText(String.valueOf(fibCurrent));
                      }
                  }
          
                  count++;
              }
          
              public void back1(View view) {
                  count = 1;
                  fibNMinus1 = 1;
                  fibNMinus2 = 0;
                  showCount.setText(getString(R.string.count_initial_value));
              }
          
              public void setLimit(View view) {
                  // Create and display a dialog to set the limit
                  AlertDialog.Builder builder = new AlertDialog.Builder(this);
                  builder.setTitle("Set Limit");
          
                  final EditText input = new EditText(this);
                  input.setInputType(android.text.InputType.TYPE_CLASS_NUMBER);
                  builder.setView(input);
          
                  builder.setPositiveButton("OK", new DialogInterface.OnClickListener() {
                      @Override
                      public void onClick(DialogInterface dialog, int which) {
                          // Get the limit from the input and set it for calculations
                          String limitStr = input.getText().toString();
                          limit = Integer.parseInt(limitStr);
                      }
                  });
          
                  builder.setNegativeButton("Cancel", new DialogInterface.OnClickListener() {
                      @Override
                      public void onClick(DialogInterface dialog, int which) {
                          dialog.cancel();
                      }
                  });
          
                  builder.show();
              }
          }

# Hasil Run

Untuk run app ini saya menggunakan software emulator yaitu Genymotion. Berikut ini adalah tampilan dari aplikasi yang telah saya buat :

* Tombol Toast ditekan, maka akan muncul message "Bilangan Fibonacci" seperti berikut

![Hasil 1 fibonacci](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/c8a1b671-2f78-4911-98da-691cb3efaace)

* Tombol Count ditekan, maka angka "1" akan berubah menjadi Bilangan Fibonacci seperti berikut

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/780a973d-d5d0-4f11-9d00-7f061a0e3c67)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/30c62bce-86a2-41ee-9f59-7eaa03d66602)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/9b81ceca-e35c-497f-934b-8dadef86086e)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/2f2bc529-17cb-453d-a21f-7b66862a2514)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/27506b03-bc0f-415f-a848-54a8d34899d1)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/7377755e-754e-4d1a-b0ed-b2e48bc40bec)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/42b0b13c-0f56-49fb-866f-945fb8e5538e)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/e585b9ea-4f12-4f84-bcf1-71212e7885da)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/856a6524-70d9-444f-bed8-f04742f62258)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/a0f5f843-a958-4078-8334-1cfa0381e11a)

![image](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/03a38517-ff0b-4c65-94b3-54773ee118cb)

* Kemudian kita juga dapat menambahkan elemen menentukan limitnya seperti berikut

https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/f1afd6f9-72c1-4898-a440-97996f50deb6

