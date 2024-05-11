# Ex.No:8 To create a gallery control using android studio to display images or photos.

## AIM:
To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:
Latest Version Android Studio

## ALGORITHM:

1. Create a New Project in Android Studio
2. Design the activity_main.xml file, which represents the Image and Gallery View.
3. Go to the MainActivity File.
4. Create a New Class ImgAdapter extended from BaseAdapter and implements the overridden methods.

## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by: Ann Blessy Philips
Registeration Number : 212222040008
*/
```

### In activity_main.xml :
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Gallery
        android:id="@+id/gallery"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.889" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="fill_parent"
        android:layout_height="fill_parent"
        android:layout_below="@+id/gallery"
        android:layout_centerHorizontal="true"
        android:scaleType="fitCenter"
        app:layout_constraintBottom_toBottomOf="@+id/gallery"
        app:layout_constraintStart_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/gallery"
        app:layout_constraintVertical_bias="0.849" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="174dp"
        android:layout_height="99dp"
        android:text="Gallery Control"
        android:textAlignment="center"
        android:textSize="28sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.045" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### In MainActivity.java :
```
package com.example.gallery_control;

import android.app.Activity;
import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.AdapterView;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class MainActivity extends Activity {
    private Integer[] mImageIds = {
            R.drawable.image1,
            R.drawable.image2,
            R.drawable.image3,
            R.drawable.image4,
            R.drawable.image5,
            R.drawable.image6,
            R.drawable.image7,
            R.drawable.image8,
            R.drawable.image9,
            R.drawable.image10,
            R.drawable.image11,
            R.drawable.image12
    };
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Gallery gallery = (Gallery) findViewById(R.id.gallery);
        gallery.setAdapter(new ImageAdapter(this));

        gallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                ImageView imageView = (ImageView) findViewById(R.id.imageView);
                imageView.setImageResource(mImageIds[position]);
            }
        });
    }
    public class ImageAdapter extends BaseAdapter {
        private Context mContext;

        public ImageAdapter(Context c) {
            mContext = c;
        }
        public int getCount() {
            return mImageIds.length;
        }
        public Object getItem(int position) {
            return null;
        }
        public long getItemId(int position) {
            return 0;
        }
        public View getView(int position, View convertView, ViewGroup parent) {
            ImageView imageView = new ImageView(mContext);
            imageView.setImageResource(mImageIds[position]);
            imageView.setLayoutParams(new Gallery.LayoutParams(150, 100));
            imageView.setScaleType(ImageView.ScaleType.FIT_XY);
            return imageView;
        }
    }
}
```

## OUTPUT
![IMG-20240411-WA0011](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/5d6ebb31-2cd4-4776-b1f6-ddfb4af3252c)         ![IMG-20240411-WA0010](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/9d4c3af0-5585-4a26-b807-facb7c6379d1)         ![IMG-20240411-WA0009](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/f1957807-4fc2-4cf9-9c32-29724b37dd11)
![IMG-20240411-WA0008](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/ab1df6d5-e1ad-42d0-acdf-7ceb5a0c83a5) ___ ![IMG-20240411-WA0007](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/9434d57d-898f-4a55-9ab0-344b17d7224e)

## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

