[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/owner/my-element)

##&lt;vr-viewer&gt;

`vr-viewer` is a container to display a VR web view using the google vr webview.
https://github.com/googlevr/vrview

It can display either one picture, or a set with hotspot to link them.

You use the configuration property to give it an object with all the infos.

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="vr-viewer.html">
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<vr-viewer configuration='{"start":"img001", "assets": {"img001":{"url":"https://storage.googleapis.com/vr-walk.appspot.com/walk/IMG_20170512_180048.vr-converted.jpg", "is_autopan_off":true,"is_stereo":true, "type":"image", "hotspot":{"hp1":{"pitch": 0, "yaw": 125, "radius": 0.05, "distance": 1, "destination":"img002"} }},"img002":{"url":"https://storage.googleapis.com/vr-walk.appspot.com/walk/IMG_20170512_180350.vr-converted.jpg", "is_stereo":true, "is_autopan_off":false, "type":"image", "hotspot":{"hp1":{"pitch": 0, "yaw": 125, "radius": 0.05, "distance": 1, "destination":"img001"} }}} }'></vr-viewer>
```

the configuration is in the form :

The configuration of the component

  ```json       
 {
  start:assetId,
  assets:{
    img001:{
      url:http://url.jpg,
      type: "video"/"image",
      is_stereo:	Boolean,	(Optional) Indicates whether the content at the image or video URL is stereo or not.
      default_yaw:	Number,	(Optional) Numeric angle in degrees of the initial heading for the 360° content. By default, the camera points at the center of the underlying image.
      preview:	String	(Optional) URL to a preview image for a 360° image file.
      is_debug:	Boolean,	(Optional) When true, turns on debug features like rendering hotspots ad showing the FPS meter.
      is_vr_off:	Boolean,	(Optional) When true, disables the VR mode button.
      is_autopan_off:	Boolean,	(Optional) When true, disables the autopan introduction on desktop.
      is_yaw_only:	Boolean,	(Optional) When true, prevents roll and pitch. This is intended for stereo panoramas.
      hotSpot:{
        hp1:{
          pitch: 30, // In degrees. Up is positive.
          yaw: 20, // In degrees. To the right is positive.
          radius: 0.05, // Radius of the circular target in meters.
          distance: 2 // Distance of target from camera in meters.
        }
      }
    }
  }
 }

Because of the underliying iframe using by the Google VR webview the url for the image MUST be absolute, and the CORS must be authorized on them
```