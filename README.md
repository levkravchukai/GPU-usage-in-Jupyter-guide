GPU using
Windows
1. Install Python 10.0 or create an environment with Python v10.0 if you have another version.
2. Update Nvidia drivers(if is needed)
3. Install Cuda v11.8 (https://developer.nvidia.com/cuda-toolkit, You need simple registration)
4. pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
5. import torch
print(torch.cuda.is_available())  # → True, якщо GPU активний

Mac (M1+)
1. Python v10.0
2. Create an environment

PyTorch
	pip install torch torchvision torchaudio
 	import torch
	print(torch.backends.mps.is_available())  # → True, якщо Metal доступний
	
4.
	conda install -c apple tensorflow-deps
pip install tensorflow-macos
pip install tensorflow-metal 
