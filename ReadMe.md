Screen Mirror // Android -> Ubuntu

Requirements-
	android-tools-adb
	ffmpeg

Steps-
	* install all the requirements
		sudo apt install android-tools-adb
		sudo apt install ffmpeg
	* enable usb debugging in android device
	* connect the android device via USB
	* list all adb devices to check if the device is connected
		adb devices
	* Open a tcpip port for communication (screen streaming)
		adb tcpip 8882
		(Now you can disconnect the usb)
	* Connect the android device through that port using device IP address
		adb connect 10.42.0.240:8882
	* display the android device screen using the below command
		adb shell screenrecord --output-format=h264 - | ffplay -
