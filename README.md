# BottomSheetDialogFragmentJava
 
[Source](https://www.geeksforgeeks.org/modal-bottom-sheet-in-android-with-examples/)

- BottomSheetDialog.java
```java
public class BottomSheetDialog extends BottomSheetDialogFragment {

    @Override
    public View onCreateView(LayoutInflater inflater, @Nullable
            ViewGroup container, @Nullable Bundle savedInstanceState) {
        View v = inflater.inflate(R.layout.bottom_sheet_layout,container, false);

        Button algo_button = v.findViewById(R.id.algo_button);
        Button course_button = v.findViewById(R.id.course_button);

        algo_button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(getActivity(), "Algorithm Shared", Toast.LENGTH_SHORT).show();
                dismiss();
            }
        });

        course_button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(getActivity(), "Course Shared", Toast.LENGTH_SHORT).show();
                dismiss();
            }
        });
        return v;
    }
}
```

- bottom_sheet_layout.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/purple_500"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="This is a Modal BottomSheet"
        android:textColor="@color/white"
        android:textSize="25sp" />

    <Button
        android:id="@+id/algo_button"
        style="@style/TextAppearance.AppCompat.Widget.Button.Colored"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:backgroundTint="@color/white"
        android:text="Share this Algorithm"
        android:textColor="@color/black" />

    <Button
        android:id="@+id/course_button"
        style="@style/TextAppearance.AppCompat.Widget.Button.Colored"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="@color/white"
        android:text="Share this Course"
        android:textColor="@color/black" />

</LinearLayout>
```

- MainActivity.java
```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btn = findViewById(R.id.open_bottom_sheet);

        btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                BottomSheetDialog bottomSheet = new BottomSheetDialog();
                bottomSheet.show(getSupportFragmentManager(),
                        "ModalBottomSheet");
            }
        });
    }
}
```

---

```
Copyright 2021 M. Fadli Zein
```