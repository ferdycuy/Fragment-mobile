# Fragment_Tab
Nama    : Ferdyana Eka Prasetya

NIM      : 312210121

Kelas    : TI.22.A.1

Dosen   : Donny Maulana, S.Kom., M.M.S.I.

### TUGAS

Buatlah fragment menu dengan tema Genre Film (Action, Komedi dan Romance) tampilan bisa berisi sinopsis film dan gambar dari film tersebut.

### Lngkah - langkah pengerjaan 
Disini, Saya masih menggunakan project sebelumnya, jadi sekarang Saya hanya tinggal menambahkan lagi satu tombol intent untuk menuju activity fragment nya.
- Pertama, kita buat sebuah class java baru, disini saya menamai classnya FragmentActivity.

> klik kanan **com.example.tugassembilan**>new>java class

- Lalu kita buat lagi tiga buah class java dan layout xml, dengan menggunakan template Fragment (blank) yang nantinya akan otomatis terbuat code java didalamnya. Caranya seperti ini:
> klik kanan java class **FragmentActivity**> Fragment> Fragment(Blank)> isi fragment_name
**NOTE**: Buat sebanyak tiga buah yaitu FirstFragment, SecondFragment, ThirdFragment.

- Buat satu buah layout lagi untuk halaman dari fragment activity ini. Saya menamainya **activity_fragment.xml**
> klik kanan layout>new>layout recouce file

- Kalau sudah, kita tambahkan terlebih dahulu beberapa baris code untuk dependencies di gradle.build.kts. Berikut adalah kodenya :

```
val fragmentVersion = "1.6.2"
implementation("androidx.fragment:fragment:$fragmentVersion")
```
> **NOTE:** jika sudah menambahkan jangan lupa untuk di sync agar gradle sinkron dengan projectnya.

- Buka **activity_fragment.xml** dan tambahkan code berikut untuk tampilan layoutnya :

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".FragmentActivity">

    <TextView
        android:id="@+id/header"
        android:layout_width="match_parent"
        android:layout_height="60dp"
        android:text="@string/movies"
        android:paddingStart="8dp"
        android:textSize="24sp"
        android:textStyle="bold"
        android:textColor="#FFFFFF"
        android:paddingTop="16dp"
        android:background="#004685"
        tools:ignore="RtlSymmetry" />

    <com.google.android.material.tabs.TabLayout
        android:id="@+id/tablayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="#004685"
        app:tabIndicator="@color/white"
        app:tabSelectedTextColor="@color/white">

        <com.google.android.material.tabs.TabItem
            android:id="@+id/tab1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/action"
            />

        <com.google.android.material.tabs.TabItem
            android:id="@+id/tab2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/comedy"
            />

        <com.google.android.material.tabs.TabItem
            android:id="@+id/tab3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/romance"
            />

    </com.google.android.material.tabs.TabLayout>


    <FrameLayout
        android:id="@+id/framelayout"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</LinearLayout>

```

- Jika sudah, lanjut buka ketiga layout tab yang sudah dibuat diawal, kepunyaan saya disini namanya **fragment_first.xml**, **fragment_second.xml**, **fragment_third.xml**. Disini saya menggunakan scroll view agar semua content dapat masuk. Masukan code berikut ke masing - masing layoutnya :
  - **fragment_first.xml**

  ```
  <?xml version="1.0" encoding="utf-8"?>
  <FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".FirstFragment">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:ignore="UselessParent" >

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <TextView
                android:id="@+id/tvMovieTitle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:textSize="24sp"
                android:textAlignment="center"
                android:textStyle="bold"
                android:text="@string/First_Fragment" />

            <ImageView
                android:id="@+id/ivMoviePoster"
                android:layout_width="250dp"
                android:layout_height="400dp"
                android:layout_marginStart="80dp"
                android:layout_marginTop="20dp"
                android:importantForAccessibility="no"
                android:scaleType="centerCrop"
                android:src="@drawable/action" />

            <TextView
                android:id="@+id/tvMovieSynopsis"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="10dp"
                android:text="@string/Sinopsis_Action"
                android:textSize="18sp" />
        </LinearLayout>
    </ScrollView>
    </FrameLayout>
    ```
  
  > **NOTE**: untuk string,drawable silahkan dibuat sesuai keingiinan

  - **fragment_second.xml**
    
  ```
    <?xml version="1.0" encoding="utf-8"?>
    <FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".FirstFragment">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:ignore="UselessParent">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <TextView
                android:id="@+id/tvMovieTitle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:textSize="24sp"
                android:textAlignment="center"
                android:textStyle="bold"
                android:text="@string/Second_Fragment" />

            <ImageView
                android:id="@+id/ivMoviePoster"
                android:layout_width="250dp"
                android:layout_height="400dp"
                android:layout_marginStart="80dp"
                android:layout_marginTop="20dp"
                android:importantForAccessibility="no"
                android:scaleType="centerCrop"
                android:src="@drawable/comedy" />

            <TextView
                android:id="@+id/tvMovieSynopsis"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="10dp"
                android:text="@string/Sinopsis_Comedy"
                android:textSize="18sp" />
        </LinearLayout>
    </ScrollView>
    </FrameLayout>
  ```
  
  > **NOTE**: untuk string,drawable silahkan dibuat sesuai keingiinan
   
  - **fragment_third.xml**

  ```
  <?xml version="1.0" encoding="utf-8"?>
  <FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".FirstFragment">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:ignore="UselessParent">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <TextView
                android:id="@+id/tvMovieTitle"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:textSize="24sp"
                android:textAlignment="center"
                android:textStyle="bold"
                android:text="@string/Third_Fragment" />

            <ImageView
                android:id="@+id/ivMoviePoster"
                android:layout_width="250dp"
                android:layout_height="400dp"
                android:layout_marginStart="80dp"
                android:layout_marginTop="20dp"
                android:importantForAccessibility="no"
                android:scaleType="centerCrop"
                android:src="@drawable/romance" />

            <TextView
                android:id="@+id/tvMovieSynopsis"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="10dp"
                android:text="@string/Sinopsis_Romance"
                android:textSize="18sp" />
        </LinearLayout>
    </ScrollView>
    </FrameLayout>
   ```
  
   > **NOTE**: untuk string,drawable silahkan dibuat sesuai keingiinan

- Setelah semua code layout berhasil dimasukkan, sekarang kita isi code untuk **FragmentActivity.java** agar projectnya bisa berjalan. Berikut adalah codenya:

```
package com.example.tugassembilan;

import android.os.Bundle;
import android.widget.FrameLayout;

import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentTransaction;

import com.google.android.material.tabs.TabLayout;

public class FragmentActivity extends AppCompatActivity {
    FrameLayout frameLayout;
    TabLayout tabLayout;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_fragment);

        frameLayout = (FrameLayout) findViewById(R.id.framelayout);
        tabLayout = (TabLayout) findViewById(R.id.tablayout);

        getSupportFragmentManager().beginTransaction().replace(R.id.framelayout,new FirstFragment())
                .addToBackStack(null)
                .commit();

        tabLayout.setOnTabSelectedListener(new TabLayout.OnTabSelectedListener() {
            @Override
            public void onTabSelected(TabLayout.Tab tab) {

                Fragment fragment = null;
                switch (tab.getPosition()) {
                    case 0:
                        fragment = new FirstFragment();
                        break;
                    case 1:
                        fragment = new SecondFragment();
                        break;
                    case 2:
                        fragment = new ThirdFragment();
                        break;
                }

                getSupportFragmentManager().beginTransaction().replace(R.id.framelayout, fragment)
                        .setTransition(FragmentTransaction.TRANSIT_FRAGMENT_OPEN)
                        .commit();
            }

            @Override
            public void onTabUnselected(TabLayout.Tab tab) {

            }

            @Override
            public void onTabReselected(TabLayout.Tab tab) {

            }
        });
    }
}
```

Project Fragment nya sudah selesaii,selanjutnyaaaaa....

### Proses Penggabungan

- Pertama - pertama, buka **activity_main.xml** terlebih dahulu untuk membuat icon tombol yang baru. Karena satu baris horizontal maximal tiga buah tombol dan kemarin sudah terisi penuh semua, maka sekarang kita harus membuat baris baru lagi untuk tombol project fragment ini. Berikut adalah codenya :

```
<LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center">

        <ImageButton
            android:id="@+id/btnFragmentActivity"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="20dp"
            android:background="@drawable/backgroundicon"
            android:onClick="btnFragmentActivity"
            android:src="@drawable/icon_fragment"
            tools:ignore="UsingOnClickInXml, SpeakableTextPresentCheck" />
    </LinearLayout>
```
> **NOTE** : tambahkan baris code ini dibawah linearlayout kedua.

- kedua, buka **MainActivity.java** dan tambahkan code intent untuk project fragmentnya. Berikut adalah codenya:

```
public void btnFragmentActivity(View view) {
    Intent fragact = new Intent(MainActivity.this, FragmentActivity.class);
    startActivity(fragact);
}
```

- Ketiga, buka AndroidManifest.xml dan tambahkan code berikut:

```
<activity
        android:name=".FragmentActivity"
        android:exported="true" />
```

SUDAH SELESAIII,LANJUTT?...HASIL RUNNYA KAWAN HEHE

## HASIL RUN


https://github.com/ferdycuy/Fragment-mobile/assets/115714443/86ce85f7-84b8-414b-afda-c54d2062935b




TERIMAKASIHH




