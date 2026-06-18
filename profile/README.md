# Project Setup

## Pre-processing

All preprocessing happens in the `Backend` repository.

The preprocessing pipeline consists of the following steps:

- Step 1: 
- Step 2: 

With these steps we go from the lidar pointcloud to a usable smoothed mesh.

## Server

After preprocessing is complete, the server can be started from the `backendRust` repository:

```bash
cargo run --release --bin server -- \
  --lidar <PATH_TO_SMOOTHED_MESH> \
  --mat <PATH_TO_MAT_FILE> \
  --port <PORT (8000 for headset) > \
  --fps <FPS>
```

The server does the raytracing of all the signals against the smoothed mesh and sits on standby 

## VR Headset Application

All code for the headset application is located in the `Vr-visualization` repository.

At the time of writing, the project requires the Oculus VR fork of Unreal Engine. Setup instructions can be found in the official Meta developer documentation:

https://developers.meta.com/horizon/documentation/unreal/unreal-quick-start-install-unreal-engine/#meta-fork

After installing and configuring the engine, the application can be built into a shipping APK.

Once the build is complete, it can be deployed to the headset by connecting it via USB-C and running the generated install script from file explorer.

The first time of running a new application it will always ask to get permission for all needed access like cameras and the scene mesh. 

And it will automatically try to connect to the server when the application starts from 0 (or by manually restarting it in settings).


