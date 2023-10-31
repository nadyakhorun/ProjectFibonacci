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

![layoutfibonacci](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/6a260f68-1d1c-45a0-a23b-36ccbd35356f)

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
          
              <EditText
                  android:id="@+id/edit_max_fibonacci"
                  android:layout_width="0dp"
                  android:layout_height="wrap_content"
                  android:layout_marginEnd="8dp"
                  android:layout_marginTop="8dp"
                  android:hint="Maksimum Fibonacci"
                  android:inputType="number"
                  app:layout_constraintEnd_toEndOf="parent"
                  app:layout_constraintTop_toTopOf="parent"
                  tools:ignore="MissingTranslation"/>
          
              <Button
                  android:id="@+id/button_toast"
                  android:layout_width="190dp"
                  android:layout_height="48dp"
                  android:layout_marginStart="8dp"
                  android:layout_marginTop="8dp"
                  android:background="@color/colorPrimary"
                  android:onClick="showToast"
                  android:textColor="@android:color/white"
                  android:text="@string/button_label_toast"
                  app:layout_constraintStart_toStartOf="parent"
                  app:layout_constraintTop_toTopOf="parent" />
          
          
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
                  app:layout_constraintTop_toBottomOf="@id/button_toast"
                  tools:ignore="RtlCompat" />
          
          </androidx.constraintlayout.widget.ConstraintLayout>

   ![activity_fibonacci](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/3d6de6b2-8ab9-413e-937f-97e2bf253e3c)

![activity fibonacci 1](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/39589147-ab9b-4be1-8ade-a389ed57ed43)

![activity fibonacci 2](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/36a466e7-743c-4253-8ade-d4349d4ec356)

![activity fibonacci 3](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/a2629bea-1f78-487a-970c-fd0c4f559a03)

  * strings.xml
 
        <resources>
            <string name="app_name">Tugasenam</string>
            <string name="button_label_toast">Toast</string>
            <string name="button_label_count">Count</string>
            <string name="count_initial_value">1</string>
            <string name="toast_message">Bilangan Fibonacci</string>
            <string name="button_label_finish">Reset</string>
            <string name="enter_fibonacci_limit">Masukan Limit Angka</string>
        </resources>

![strings xml](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/99c5cbf2-589a-46ae-be2a-71115396efde)

* colors.xml
   
           <?xml version="1.0" encoding="utf-8"?>
           <resources>
                <color name="black">#FF000000</color>
                <color name="white">#FFFFFFFF</color>
                <color name="colorPrimary">#3F5185</color>
                <color name="colorPrimaryDark">#303F9F</color>
                <color name="colorAccent">#FF4081</color>
            
            </resources>

![colors xml](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/de37bafb-2c7d-4f2f-b7b0-464c255b4206)

  # Tampilan Design

 ![tampilan design baru](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/01b1df84-7b1f-4c8a-95f4-baf64ea60b3e)

  # MainActivity.java

  Pada MainActivity.java berisi semua codingan untuk fungsi-fungsinya. Seperti, fungsi untuk 
  tombol-tombol dan rumus bilangan fibonaccinya.

         package com.tugasenam;

            import android.os.Bundle;
            import android.view.View;
            import android.widget.EditText;
            import android.widget.TextView;
            import android.widget.Toast;
            
            import androidx.appcompat.app.AppCompatActivity;
            
            public class MainActivity extends AppCompatActivity {
                private TextView showCount;
                private int count = 0;
                private long fibNMinus1 = 1;
                private long fibNMinus2 = 0;
                private EditText edit_max_fibonacci;
            
                @Override
                protected void onCreate(Bundle savedInstanceState) {
                    super.onCreate(savedInstanceState);
                    setContentView(R.layout.activity_fibonacci);
            
                    showCount = findViewById(R.id.show_count);
                    edit_max_fibonacci = findViewById(R.id.edit_max_fibonacci);
            
                    updateCountDisplay();
            
                    fibNMinus1 = 1;
                    fibNMinus2 = 0;
                }
            
                private void updateCountDisplay() {
                    showCount.setText(String.valueOf(fibNMinus1));
            
                    if (count % 4 == 0) {
                        showCount.setTextColor(getResources().getColor(R.color.colorPrimary));
                    } else if (count % 4 == 1) {
                        showCount.setTextColor(getResources().getColor(R.color.colorAccent));
                    } else if (count % 4 == 2) {
                        showCount.setTextColor(getResources().getColor(R.color.colorPrimary));
                    } else {
                        showCount.setTextColor(getResources().getColor(R.color.colorAccent));
                    }
                }
            
                public void showToast(View view){
                    Toast.makeText(this, "Bilangan Fibonacci",
                            Toast.LENGTH_SHORT).show();
                }
            
                public void countUp(View view) {
                    int maxFibonacci = Integer.parseInt(edit_max_fibonacci.getText().toString());
            
                    if (count >= maxFibonacci) {
                        Toast.makeText(this, "Maksimum Fibonacci tercapai", Toast.LENGTH_SHORT).show();
                        return;
                    }
            
                    long fibCurrent;
                    if (count == 0 || count == 1) {
                        fibCurrent = 1;
                    } else {
                        fibCurrent = fibNMinus1 + fibNMinus2;
                    }
            
                    fibNMinus2 = fibNMinus1;
                    fibNMinus1 = fibCurrent;
                    updateCountDisplay();
            
                    count++;
                }
            
                public void back1(View view) {
                    count = 0;
                    fibNMinus1 = 1;
                    fibNMinus2 = 0;
                    updateCountDisplay();
                }
            }

![mainactivity1](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/20cef6a1-a9aa-4820-8830-85c804580dda)

![mainactivity2](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/12e6e763-2f50-4f22-bffe-7c3cc2ecad08)

![mainactivity3](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/b1c260dc-de07-4dba-92b0-c49b6a7aa859)

# Hasil Run

Untuk run app ini saya menggunakan software emulator yaitu Genymotion. Berikut ini adalah tampilan dari aplikasi yang telah saya buat :

* Tombol Toast ditekan, maka akan muncul message "Bilangan Fibonacci" seperti gambar dibawah

![hasil fibonacci 1](https://github.com/nadyakhorun/ProjectFibonacci/assets/115801823/b0b2797e-6737-4045-88cc-8dcf41ccc7cf)

* Tombol Count ditekan, maka angka "1" akan berubah menjadi Bilangan Fibonacci seperti berikut.
  
