# @angelcat/rn-pdf-thumbnail

This library is forked from [react-native-pdf-thumbnail](https://www.npmjs.com/package/react-native-pdf-thumbnail).

A react native module for generating thumbnail for PDF files.

A wrapper for:
- PDFKit on iOS (requires iOS 11+)
- PdfRenderer on Android (requires API level 21 - LOLLIPOP)

No other JavaScript or native dependencies.

Note: This module **does not** work in Expo.

## Installation

```sh
npm install @angelcat/rn-pdf-thumbnail
# or
yarn add @angelcat/rn-pdf-thumbnail
```

## Usage

```js
import PdfThumbnail from "@angelcat/rn-pdf-thumbnail";

// For iOS, the filePath can be a file URL.
// For Android, the filePath can be either a content URI, a file URI or an absolute path.
const filePath = 'file:///mnt/sdcard/myDocument.pdf';
const page = 0;

// The thumbnail image is stored in caches directory, file uri is returned.
// Image dimensions are also available to help you display it correctly.
const { uri, width, height } = await PdfThumbnail.generate(filePath, page);

// Generate thumbnails for all pages, returning an array of the object above.
const results = await PdfThumbnail.generateAllPages(filePath);

// Default compression quality is 80, you can optionally specify a quality between 0 and 100.
const { uri, width, height } = await PdfThumbnail.generate(filePath, page, 95);
const results = await PdfThumbnail.generateAllPages(filePath, 90);
```

## Demo

The example app contains a document picker, it generates and displays a thumbnail for the selected PDF file.

To run it:
```sh
yarn
yarn example ios
yarn example android
```

iOS | Android
------- | ---
![86563759-d103db80-bf19-11ea-98a2-77788efe4938](https://user-images.githubusercontent.com/3325682/86644851-bfaae580-bf92-11ea-8b2b-f065784b3425.png) | ![86564313-dca3d200-bf1a-11ea-99fe-6f08a3302b20](https://user-images.githubusercontent.com/3325682/86644858-c174a900-bf92-11ea-8a01-79476b1050a1.png)

## Contributing

See the [contributing guide](CONTRIBUTING.md) to learn how to contribute to the repository and the development workflow.

## License

MIT
