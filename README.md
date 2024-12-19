# Expo Unhandled Promise Rejection with Native Modules

This repository demonstrates a common issue in Expo's managed workflow: unhandled promise rejections when using native modules that aren't fully compatible with the managed environment.  The `bug.js` file shows example code that might trigger this error, while `bugSolution.js` offers solutions.

## Problem

Expo's managed workflow simplifies development, but it has limitations when interacting with native modules.  If a module has extensive native dependencies, you might encounter unexpected errors like unhandled promise rejections during the build or runtime.  This is often due to the limitations of Expo Go or conflicts with the way Expo handles native code.

## Solution

The main solutions are:

1. **Use an Expo compatible alternative:** Check if an Expo-compatible version or alternative exists for the native module you are using. Expo's documentation and community forums are good places to search for compatible packages.
2. **Eject to bare workflow:** If no suitable alternative is available, consider ejecting to Expo's bare workflow. This gives you more control over native code integration but requires more manual configuration and maintenance.
3. **Check SDK Version Compatibility:** Ensure your Expo SDK version is compatible with the native module's declared requirements. Incompatibilities between versions can cause similar errors. 
4. **Properly Handle Async Operations:** Ensure that you handle any asynchronous operations within native modules correctly. This often involves using appropriate error handling mechanisms such as `.catch()` blocks to gracefully handle any promise rejections.