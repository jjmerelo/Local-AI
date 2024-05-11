## Install Stable Diffusion (for image generation)
1. Install Pre-requirements:
```
sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git
```
2. Install pyenv:
```
curl https://pyenv.run | bash
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
```
3. Install Python 3.10 and make it global default:
```
pyenv install 3.10
pyenv global 3.10
```
4. Install Stable Diffusion:
```
mkdir stablediff
cd stablediff/
wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
chmod +x webui.sh
./webui.sh --listen --api
```
You will now see a ![image](https://github.com/jjmerelo/Local-AI/assets/169418683/3719d4c7-b293-405e-b5a9-8bd745497b73) icon under your WebUI replies. Click on that button to generate an image.

Additionally, access the web UI at http://localhost:7860/ for custom optimazation and configutations.

5. Note: if you close the terminal/cmd window..to reaccess Stable Diffusion you will need to rerun: 
```
cd stablediff/
./webui.sh --listen --api
```

![image](https://github.com/jjmerelo/Local-AI/assets/169418683/4585a5e1-769f-4823-99f9-0eb9be1cbbcd)


![image](https://github.com/jjmerelo/Local-AI/assets/169418683/bc0d3309-a861-4d4e-bd74-8a2e5b484cad)
