# Debugging Cheat Sheet
A sheet of common bugs I run into and how to quickly resolve them with explanations 

## REACT NATIVE

Execution failed for task ':app:checkDebugDuplicateClasses
- Add ‘android.enableJetifier=true’ to gradle.properties

Task :react-native-pager-view:compileDebugKotlin FAILED
- Go to node_modules/react-native-pager-view/android/src/paper/java/com/reactnativepagerview/PagerViewViewManager.kt
- Remove ? from child: View? in addView
- Remove ? from String? In receiveCommand 

TypeError: Network request failed
- Reason: Mobile device doesn’t have access to computer local port
- Solution: Forward port with adb
    adb reverse tcp:8163 tcp:8163

app:installDebug FAILED
- Install it again. Third time’s the charm

Invariant violation turbomodule vector icons could not be found
- Solution: Download the fonts needed for the specific icon package

## SQL
Constantly freezing/not responding SQL Developer
- Solution: Increase memory for SQL
- Go to ~/.sqldeveloper/[version-name]/product.conf
- Fix the 3rd last line to AddVMOption  -Xmx1024M, or crank up as much as you like

## GIT
remote end hung up unexpectedly
- Solution: Crank up file size limit
- git config --global http.postBuffer 524288000

