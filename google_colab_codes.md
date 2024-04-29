# Run first - we need to install the required dependencies and then clone the latest version of Fooocus
!pip install pygit2==1.12.2
%cd /content
!git clone https://github.com/jaymarcansancio/Fooocus.git
%cd /content/Fooocus

# Move this block into separate code if needed
# Install any additional Fooocus dependencies e.g. upscaler
!wget -O /content/Fooocus/models/upscale_models/fooocus_upscaler_s409985e5.bin https://huggingface.co/lllyasviel/misc/resolve/main/fooocus_upscaler_s409985e5.bin?download=true

# Move this block into separate code if needed
# Download the model you want to run and save it to the checkpoint folder
!wget -O /content/Fooocus/models/checkpoints/epicRealism_xl.safetensors https://civitai.com/api/download/models/461409?type=Model&format=SafeTensor&size=pruned&fp=fp16

# Move this block into separate code if needed
# Run Fooocus!
!python entry_with_update.py --share --always-high-vram