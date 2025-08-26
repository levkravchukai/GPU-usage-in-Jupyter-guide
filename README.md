<img width="1280" height="586" alt="image" src="https://github.com/user-attachments/assets/186f5a1f-65c2-49b2-b46a-1984bc942bbc" />GPU using
Windows
1. a. Install Python 10.0, don't forget to add to the Path via installing
1. b. If you have another version, install Python 10.0, or if you don't want to install this version of Python, please download zip version of Python and unpack it wherever you want
2. Select Folder(cd your path to project folder) for environment and create an environment(Disk_letter:\Your_path\Python310\python.exe -m venv gpu_env)
3. Update Nvidia drivers(if needed)
4. Install Cuda v11.8 (https://developer.nvidia.com/cuda-toolkit, You need simple registration)
5. Activate your environment Disk_letter:\Your_path\gpu_env\Scripts\Activate.ps1
6. pip install -r requirements.txt --extra-index-url https://download.pytorch.org/whl/cu118
7. import torch
   print(torch.cuda.is_available())  # → True, якщо GPU активний

Mac (M1+)
1. Python v10.0
2. Create an environment
3. PyTorch
 	1. Install
	pip install torch torchvision torchaudio
	2. Check
    	import torch
		print(torch.backends.mps.is_available())  # → Should be: True
    4. Use
       Automatically 
	
5. Tensorflow
 	1. Install
		conda install -c apple tensorflow-deps
		pip install tensorflow-macos
		pip install tensorflow-metal
	2. Check
    	import tensorflow as tf
		print(tf.config.list_physical_devices('GPU'))
    4. Use
		with tf.device('/GPU:0') for using GPU

  	Example:
   		def process_images(
			#your code
   )
   		for phase in phases:
   			with tf.device('/GPU:0')
   				processed = process_images(dict[phase][0])
   			print(f"Processing of phase{phase} completed")
  	
