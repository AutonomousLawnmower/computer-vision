### First
Install Picamera2, don't use pip:
	- sudo apt install -y python3-picamera2

If there's error with libraries not existing, run:
	- source setup_rpi_for_tflite.sh

To run the model:
	- python detect_picam64.py
		- There may be some error with Serial or the Picamera2 library itself, I couldn't test w/o the camera. Navigate https://datasheets.raspberrypi.com/camera/picamera2-manual.pdf if needed.

File grass0_new.tflite is the trimmed down version of the original model, meant to be more accurate and ommitted of low-res and blurry images. But due to the lack of training images, accuracy might've actually dropped. Recommended # of images to use is ~80, I only have 60 at the moment.

If you want to use alternative files, here's grass1.tflite for example, run:
	- python detect_picam64.py --model grass1.tflite

The numbering just means the EfficientDet# model number. From 0-5 or something, with the higher numbers meaning lesser frames and more accuracy,
