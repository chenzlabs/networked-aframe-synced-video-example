# networked-aframe-synced-video-example

[A-Frame](https://aframe.io) example using [networked-aframe](https://github.com/networked-aframe/networked-aframe) with a custom component for roughly synchronized multi-user video viewing.

This example was built with [Networked-A-Frame](https://github.com/networked-aframe/networked-aframe), a web framework for building multi-user virtual reality experiences. Works on Vive, Rift, desktop, mobile platforms.

The approach taken here is to statically define a singleton video as part of the scene and expose the video's transport characteristics with a custom component `video-transport`, so that networked-aframe can handle the data synchronization.

When trying to synchronize video position, care needs to be taken to avoid 

Creating singleton objects in networked-aframe is not yet encapsulated in a component; the crude approach taken here is to define the singleton(s) by using an explicit `networkId` value and no initial owner (more specifically, an initial `owner` that is invalid), along with JavaScript that waits a little bit to see if a client is the only/first, and if so then takes ownership of the singleton(s).

Enjoy!
- M