# Camera intelligent autozoom - Flutter

#### [Qualification task for GSoC 2023](https://ccextractor.org/public/gsoc/takehome/#camera-with-intelligent-autozoom-in-flutter) - CCExtractor Development.

## Working logic of this app

- Camera preivew gives livestream of the objects
- this livestream is loaded into the **tflite** model
- we run the model & get the **percentage confidence** (probabilities) of the detected object
- if the **confidence** > 60 % then the object is assumed to be in foreground
- camera zooms on that object

## Look & feel of the app

_Camera zooms to the chair because it has the highest probabilty (>= 60%) of being in the foreground. Then it zooms to the laptop since the camera is moved_

![](https://github.com/DivS-15/camera_intelligent_autozoom_gsoc23/blob/master/gsoc23_1.gif)


## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## Build this project

1. Dependencies

Camera package - 

```

$ flutter pub add camera

```

Tflite package - 

```

$ flutter pub add tflite

```




