# WebRTC Video/Audio Broadcast

WebRTC PeerToPeer broadcast application that allows the broadcaster to send a video and audio stream to all connected users (watchers).

You can find the tutorial that explains the code and functionality on my [website](https://gabrieltanner.org/blog/webrtc-video-broadcast).

## Getting started

### Starting the application

Start the application using Node:

```bash
# Install dependencies for server
npm install

# Run the server
node server
```

Start the application using Docker:

```bash
# Building the image
docker build --tag webrtcvideobroadcast .

# Run the image in a container
docker run -d -p 4000:4000 webrtcvideobroadcast
```

### Testing the application

The application should now be running on your localhost:4000 and you test it by connecting to localhost:4000/broadcast.html to add a new broadcaster.

After that, you just need to visit localhost:4000 to connect to the server as a client and you should get the video that is streamed from the broadcaster.

## Adding a TURN server

A TURN server is used to relay traffic if a direct peer-to-peer connection fails and is required for most WebRTC applications since a direct connection is often not possible between two clients that aren't on the same network. This repository doesn't include the usage of a TURN server by default, but you can add one by commenting in the turn configuration in the `broadcast.js` and `watch.js` file and filling in your TURN credentials.

There are several options on how you can create your own TURN server. Here are just two common ones:

- [Coturn](https://github.com/coturn/coturn)
- [Golang WebRTC pion library TURN examples](https://github.com/pion/turn/tree/master/examples)

You can also use TURN servers from cloud providers or other companies. Here is a [tutorial](https://gabrieltanner.org/blog/turn-server) that shows you how to set up Coturn and add a domain to your TURN server.

## Author

Gabriel Tanner

## Support me

<a href="https://www.buymeacoffee.com/gabrieltanner" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details
