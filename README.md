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

![IMG-20240411-WA0011](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/ff8b0cf4-4e9a-46f0-8aad-e3d4d3d5c095)

![IMG-20240411-WA0010](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/9f66bc8a-4532-40ac-9822-be6f1dcfde02)

![IMG-20240411-WA0009](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/e0e025ba-2362-4cf5-9532-a50b6c231289)

![IMG-20240411-WA0008](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/732eefce-1256-4a68-ba5c-efe5143bdaf9)

![IMG-20240411-WA0007](https://github.com/AnnBlessy/gallerycontrol/assets/119477835/d15bc7b8-d344-4beb-8458-c12e5225a331)



## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

