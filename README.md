# react-ns-embed

This project demonstrates how NativeScript can be added to a React Native project as a cocoapod dependency. Before building it run `pod install` .

### Notes

```
require_relative '../ios/nativescript.rb'
```

This script has some methods updating the xcode project with the build steps and settings needed for the NativeScript runtime to work as well as for generating the metadata. It implements `nativescript_post_install(installer)` which should be called from the `post_install` block.

```
post_install do |installer|
  react_native_post_install(installer)
  __apply_Xcode_12_5_M1_post_install_workaround(installer)
  nativescript_post_install(installer)
end
```

