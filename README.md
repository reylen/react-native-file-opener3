react-native-file-opener
-
A React Native module that allows you to open a file (mp3, mp4, pdf, word, excel, dwg etc.) on your device with its default application

New add podspec, pod manager. No need to react-native link this file.

iOS | Android
------- | ----
<img title="iOS" src="https://github.com/huangzuizui/react-native-file-opener/blob/master/assets/ios_screen.gif"> | <img title="Android" src="https://raw.githubusercontent.com/huangzuizui/react-native-file-opener/master/assets/android_screen.gif">

# Install
##iOS
1. `npm install react-native-file-opener --save`

2. Compile and have fun

##Android
* `npm install react-native-file-opener --save`


##Usage
1. In your React Native javascript code, bring in the native module
```javascript
const FileOpener = require('react-native-file-opener');
```
2. Basic usage
```javascript
const FilePath = ...; // path of the file
const FileMimeType = ...; // mime type of the file
FileOpener.open(
    FilePath,
    FileMimeType
).then((msg) => {
    console.log('success!!')
},() => {
    console.log('error!!')
});
```
##Usage with react-native-fs
* You can get filepath by using [react-native-fs](https://github.com/johanneslumpe/react-native-fs)

```javascript
const RNFS = require('react-native-fs');
const FileOpener = require('react-native-file-opener');

const SavePath = Platform.OS === 'ios' ? RNFS.DocumentDirectoryPath : RNFS.ExternalDirectoryPath;
const sampleDocFilePath = SavePath + '/sample.doc';

...

  function openSampleDoc() {
        FileOpener.open(
            sampleDocFilePath,
            'application/msword'
        ).then(() => {
            console.log('success!!');
        },(e) => {
            console.log('error!!');
        });

    }
    
...
```
##Demo project
[https://github.com/huangzuizui/react-native-file-opener-demo](https://github.com/huangzuizui/react-native-file-opener-demo)
