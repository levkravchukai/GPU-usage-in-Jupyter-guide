# Windows
## Python
1.
- a. Install **Python 10.0**. Don't forget to add to the **PATH** via installing
- b. If you have another version, install **Python 10.0**, or if you don't want to install this version of Python, please download zip version of Python and unpack it wherever you want
2. Select **folder** for environment
	```
	cd your path_to_project_folder 
	```
3. Create an environment
	```
	Disk_letter:\Your_path\Python310\python.exe -m venv gpu_env
	```
## Nvidia
1. Update Nvidia drivers(if needed)
 - Install CUDA v11.8 (https://developer.nvidia.com/cuda-toolkit, You need simple registration) and cudnn
 - Or you can download from https://drive.google.com/drive/folders/1Fu93QXPQo9U9D7AIdsdyUnBEnskrFwD8?usp=drive_link
2. Install CUDA
   - Unzip the archive
		- Copy files from **bin** to  
	      ```
	       C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\bin
	      ```
	    - Copy files from **include** to  
	      ```
	      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\include
	      ```
	    - Copy files from **lib** to  
	      ```
	      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\lib\x64
	      ```
   - Add to PATH in Environment Variables of Windows  
      ```
      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\bin
      ```
## Packages
1. Activate your environment
	```
	Disk_letter:\Your_path\gpu_env\Scripts\Activate.ps1
	```
2. Install requirements
This is required versions of libraries:
	- torch
	- tensorflow
	- numpy
	-  pandas
	-  scipy
	-  scikit-learn
	-  statsmodels
	-  jupyter
	-  ipykernel
	-  ipywidgets

You can remove unnecessary libraries from Requirements.txt file
```
pip install -r Requirements.txt --extra-index-url https://download.pytorch.org/whl/cu118
```
## Check
	import torch
   	print(torch.cuda.is_available())  # → True, якщо GPU активний

# Mac (M1+)
1. Python v10.0
2. Create an environment
## 3. PyTorch
### Install
	pip install torch torchvision torchaudio
### Check
    	import torch
		print(torch.backends.mps.is_available())  # → Should be: True
### Use
       Automatically	
## 4. Tensorflow
### Install
		conda install -c apple tensorflow-deps
		pip install tensorflow-macos
		pip install tensorflow-metal
 ### Check
    	import tensorflow as tf
		print(tf.config.list_physical_devices('GPU'))
### Use
		with tf.device('/GPU:0') for using GPU
### Example:
	def process_images(
		#your code)
	for phase in phases:
		with tf.device('/GPU:0')
			processed = process_images(dict[phase][0])
		print(f"Processing of phase{phase} completed")
  	
