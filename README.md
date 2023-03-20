# Camera intelligent autozoom - Flutter

Qualification task for Flutter - CCExtractor Development.

## Working logic of this app

- Camera preivew gives livestream of the objects
- this livestream is loaded into the **tflite** model
- we run the model & get the percentage confidence (probabilities) of the detected object
- if the **confidence** > 60 % then the object is assumed to be in foreground
- camera zooms on that object

### Accompanying code

```dart
runModel() async {
    recognitionsList = (await Tflite.detectObjectOnFrame(
      bytesList: cameraImage.planes.map((plane) {
        return plane.bytes;
      }).toList(),
      imageHeight: cameraImage.height,
      imageWidth: cameraImage.width,
      imageMean: 127.5,
      imageStd: 127.5,
      numResultsPerClass: 1,
      threshold: 0.4,
    ))!;
    recognitionsList.forEach((element) {
      if (element['confidenceInClass'] >= 0.6) {
        setState(() {
          cameraController.setZoomLevel(3.0);
        });
      }
    });

    setState(() {
      cameraImage;
    });
  }
  
  ```
  

## Screenshots


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




