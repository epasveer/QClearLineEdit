# QClearLineEdit

QLineEdit that better handles the 'clear' action.

The Qt QLineEdit can have a 'clear' button in the text field. This is enabled
with the:
```
    QLineEdit::setClearButtonEnabled(bool enable)
```
function.

Clicking on this button clears the text field.  *However*, it doesn't emit any signal.
You must programatically check the text field. :^(


QClearLineEdit is an extension to QLineEdit.  It adds another mode for the 'clear'
button to emit the 'returnPressed' signal.

```
    // Create the LineEdit
    QClearLineEdit* lineEdit = new QClearLineEdit(parent);

    // Enable the new signal
    lineEdit->enableReturnPressedOnClear();

    // Connect the signal to our method
    QObject::connect(lineEdit, &QLineEdit::returnPressed,     this, MyClass::handleReturnPressed);
```


