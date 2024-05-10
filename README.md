# Local-AI

# Local-AI

https://ollama.com/download/linux
Download the Linux version: curl -fsSL https://ollama.com/install.sh | sh

open CMD
type wsl --install
create username password
sudo apt update
sudo apt upgrade
curl -fsSL https://ollama.com/install.sh | sh
// browse to http://localhost:11434/ to make sure it's running

ollama pull llama2
ollama run llama
Once it's running you can ask it a question and interact (like chatgpt)

Run the commands here to install docker: https://docs.docker.com/engine/install/ubuntu/
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update


sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
verify with sudo docker ps
open up http://localhost:8080/ and create an account

Select your model:
![image](https://github.com/Toteroni/Local-AI/assets/13453157/37771ee3-d15b-4216-8b52-376da00350cb)
download other models:
ollama pull codegemma
ollama pull mistral
ollama pull llama3
ollama pull gemma:7b
ollama pull llava
ollama pull dolphin-mistral
ollama pull solar https://huggingface.co/upstage/SOLAR-10.7B-Instruct-v1.0
etc..



What the UI does:
Upload files
create user accounts for family members
  set restrictions for kids account (don't do homework, instead teach where to look)
create custom models


install pyget reqs:
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git

install pyenv:
curl https://pyenv.run | bash

load pyenv automatically:
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"


source.bashrc

pyenv -h

pyenv install 3.10

pyenv global 3.10
mkdir stablediff
cd stablediff/
wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh

chmod +x webui.sh

./webui.sh --listen --api

http://localhost:7860/

