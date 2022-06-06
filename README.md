# QClearLineEdit

A version of QLineEdit that better handles the 'clear' action.

The Qt QLineEdit can have a 'clear' button in the text field. This is enabled
with this function :
```
    QLineEdit::setClearButtonEnabled(bool enable)
```


Clicking on this button clears the text field.  *However*, it doesn't emit any signal.
You must programatically check the text field. :^(


QClearLineEdit is an extension of QLineEdit.  It adds a way for the 'clear'
button to emit the 'returnPressed' signal.

```
    // Create the LineEdit
    QClearLineEdit* lineEdit = new QClearLineEdit(parent);

    // Enable the new signal
    lineEdit->enableReturnPressedOnClear();

    // Connect the signal to our method
    QObject::connect(lineEdit, &QLineEdit::returnPressed,     this, MyClass::handleReturnPressed);
```

## To use:
Copy QClearLineEdit.h and QClearLineEdit.cpp to your project. Where ever you use QLineEdit, you can use
QClearLineEdit. Enable the new signal by calling:
```
    lineEdit->enableReturnPressedOnClear();
```
QClearLineEdit can be used in 'Designer' by promoting 'QClearLineEdit' from 'QLineEdit'.


