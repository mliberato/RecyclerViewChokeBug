# RecyclerViewChokeBug

Sample app to reproduce "choke" error in RecyclerView with wrap_content in lollipop+ devices (support library 23.2.0) as reported here https://code.google.com/p/android/issues/detail?id=202216

Suggested workaround is to set nested scrolling enabled to false. Programmatically:

```java
RecyclerView recyclerView = (RecyclerView) findViewById(R.id.recycler);
recyclerView.setAdapter(adapter);
recyclerView.setNestedScrollingEnabled(false);
```

Or, if using databinding, directly in XML:

```xml
<android.support.v7.widget.RecyclerView
    android:id="@+id/recycler"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    app:layoutManager="android.support.v7.widget.LinearLayoutManager"
    app:nestedScrollingEnabled="@{false}"
    />
```
