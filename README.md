# Camera intelligent autozoom - Flutter


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

### Build this project

1. Dependencies

Camera package - 

```

$ flutter pub add camera

```

Tflite package - 

```

$ flutter pub add tflite

```




