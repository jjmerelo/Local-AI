
# Local-AI
This repo  helps you quickly set up local AI on your personal computer. You can do things like:
1. Giving family members access
   
![image](https://github.com/user-attachments/assets/a4569c4f-721b-4bee-9cc3-5adc9f11b2c7)

2. Integrating Stable Diffusion for image generation

![image](https://github.com/user-attachments/assets/9243358a-1b3d-48ea-94cf-ad5333b1eecc)

3. Connecting your LocalAI with VSCode for your own CoPilot

![image](https://github.com/user-attachments/assets/d2b671c0-590c-4496-8ea1-a42547072e73)

4. Setting up a WebCrawler to extract information from webpages
 
![image](https://github.com/user-attachments/assets/cb79e4f0-6439-44a7-9db6-fdea51fb5746)

Follow the steps below according to your operating system.

Windows users begin with Step 1.

Linux users start at Step 2.



## Step 1 - Install WSL
To install Windows Subsystem for Linux (WSL):

1. Open Command Prompt.
```
wsl --install
```
2. Follow the instructions to install WSL.
3. Create a username and password when prompted.
4. Update and upgrade your packages:
```
sudo apt update
sudo apt upgrade
```

## Step 2 - Install Ollama
1. Download the Ollama installation script:
```
curl -fsSL https://ollama.com/install.sh | sh
```
Navigate to http://localhost:11434/ to confirm it's running.

2. Pull and run the Llama2 model:
```
ollama pull llama2
ollama run llama2
```

## Step 3 - Install Docker
1. Update your package index and install prerequisites:
```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
2. Install Docker packages:
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Step 4 - Deploy WebUI container (your own site)
1. Run Docker container for WebUI:
```
sudo docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```
Verify the Docker container is running with ```sudo docker ps```.

Open http://localhost:8080/ and create an account.

2. Pull additional models as needed:
```
ollama pull codegemma
ollama pull llava
ollama pull gemma:7b
etc...
```
