# microphone-recorder

>  It is a lib for sound recording on HTML, implemented by audioContext and webWorker

**NOTE:** forked from [@bigear](https://github.com/wahengchang/bigear/tree/master/packages/microphone-recorder) and published as an ES5 compatible package.


## Install
```
$ npm install --save @cenobitedk/microphone-recorder
```


## Usage

```js

import Recorder from "@cenobitedk/microphone-recorder";


navigator.mediaDevices.getUserMedia({ audio: true }).then((mediaStreamObject) => {
    const input = audio_context.createMediaStreamSource(mediaStreamObject);

    const recorder = new Recorder(input);
    recorder.record();

    // speak for a bit
    recorder.stop();
    recorder.exportWAV("audio/wav", function(blob) {
        // append the audio blob to html element
        const url = URL.createObjectURL(AudioBLOB);
        const au = document.querySelector("audio");
        au.controls = true;
        au.src = url;
        recorder.clear();
    });
})

```

