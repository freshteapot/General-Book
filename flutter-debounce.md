```dart
Timer? _debounce;

void onTextChanged(String text) {
  if (_debounce?.isActive ?? false) _debounce!.cancel();
  _debounce = Timer(const Duration(milliseconds: 500), () {
    print("Searching for $text");
  });
}
```
