# openvidu-audio-volume-detection-error
Hello World to demonstrate the error caused by streamAudioVolumeChange

This is the exact same as the OpenVidu Hello World documented here: https://openvidu.io/docs/tutorials/openvidu-hello-world/

I am on a windows machine so I have changed my OPENVIDU_SERVER_URL to https://192.168.99.100:4443. If you use Linux/Mac please comment out line 64 of app.js and uncomment line 62.

To demonstrating that streamAudioVolumeChange is broken I have added lines 25-27 of app.js.

```javascript
publisher.on('streamAudioVolumeChange', (event) => {
	console.log('Publisher audio volume change from ' + event.value.oldValue + ' to' + event.value.newValue);
});
```

When connecting to the session with a generated token the following error is thrown.
> There was an error connecting to the session: undefined Cannot read property 'jquery' of undefined

The OpenVidu session and video continues to work but the console.log never fires.
