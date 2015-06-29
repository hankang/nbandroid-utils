# Introduction #
The class com.neenbedankt.android.test.InstrumentationTestRunner extends [android.test.InstrumentationTestRunner](http://www.google.com/codesearch/p?hl=nl#q1EHOuTuLTM/frameworks/base/test-runner/android/test/InstrumentationTestRunner.java&q=instrumentationtestrunner%20android&sa=N&cd=1&ct=rc) to output a junit report style xml report that is compatible with [Hudson](http://hudson-ci.org), so that the results and trends can be displayed.

# Usage #
  1. Drop [InstrumentationTestRunner.java](http://code.google.com/p/nbandroid-utils/source/browse/src/com/neenbedankt/android/test/InstrumentationTestRunner.java?repo=testutils) in your test project, or drop the jar file in your project.
  1. Change the AndroidManifest.xml of your test project to use com.neenbedankt.android.test.InstrumentationTestRunner like this:
```
<manifest ..>
<instrumentation android:targetPackage="com.neenbedankt.enginewatch" android:name="com.neenbedankt.android.test.InstrumentationTestRunner" />
</manifest>
```
# Running the tests #
Just run your test like you used to, but make sure you use **com.neenbedankt.**android.test.InstrumentationTestRunner. From an Android ant build you can set the property `test.runner` to this class.

After the tests have run, the file TEST-all.xml will be created in the files directory of your application on your device or emulator. For example, if the application under test is "com.myapp.superapp" the TEST-all.xml will be under "/data/data/com.myapp.superapp/files/TEST-all.xml". You can then pull this file off the device and put it somewhere your next build step or Hudson can find it.