# drive-safe-docker

# drive-safe-docker
A dockerized Flask API to predict the driver's state (`Safe Driving`, `Texting`, `Operating radio`, `Drinking`, `Reaching behind`) on a live webcam feed. 

Using docker, you can deploy this REST API on your machine very easily by following the steps below.

### Steps
1. Install docker
2. Start the docker 
3. Give permission to docker to use your laptop's webcam
`xhost local:docker` `xhost +`
`--device=/dev/video0:/dev/video0`
`--device /dev/video0`
`-v /dev/video0:/dev/video0`

`sudo cp opencv-3.2.0/build/lib/cv2.so /usr/local/lib/python3.6/dist-packages/cv2/`
`sudo cp <path to opencv source repo>/build/lib/python3/cv2.cpython-35m-x86_64-linux-gnu.so /usr/local/lib/python3.5/dist-packages/cv2/cv2.cpython-35m-x86_64-linux-gnu.so`

3. Follow the next steps from either Option 1 or Option 2

## Option 1: Pull the docker image from registry (Recommended)
I have published the docker image in the ___ registry. You can directly pull the image to your local system using:

`docker pull `


## Option 2: Build the docker image from code
`docker build -t <image_name>:<tag> .`

You can give any `<image_name>` and `<tag>` of your choice. [Here]() are some recommended naming conventions.

`docker run --name <container_name> -p <local_port>:<container_port> <image_name>:<tag>`
Specifies a name with which you can refer to your container in subsequent commands

## References
This repo uses a deep learning Keras model trained on [this]() Kaggle dataset. If you are interested to see how the model was trained, refer [here]().
