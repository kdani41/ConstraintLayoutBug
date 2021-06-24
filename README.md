## Description 

Barrier in constraint layout is matching to maximum percent specified in the <include> layout params.

Checkout `fragment_register.xml`. 


In this `include` I am including `item_email.xml` and specifying maximum width percentage of 40% by using  `layout_constraintWidth_percent`. 
By default, this include layout width should wrap but instead it ends up taking 40%.


```xml

    <androidx.constraintlayout.widget.Barrier
        android:id="@+id/barrier"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:barrierDirection="start"
        app:constraint_referenced_ids="email_cc"
        />

    <include
        android:id="@+id/email_cc"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginEnd="34dp"
        app:layout_constraintBottom_toTopOf="@+id/password_text"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/include_avatar_picker"
        app:layout_constraintWidth_max="wrap"
        app:layout_constraintWidth_percent="0.4"
        layout="@layout/item_email"/>
```  

## This works fine in following conditions

- If I remove include and directly use the view.
- If I use constraintLayout version 1.1.3. Only latest constraint layout >2.0.0 has this issue.