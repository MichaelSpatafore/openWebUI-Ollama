# openWebUI-Ollama
If you just want the commands, It will be in commands
These are the steps I did to create an Open WebUI server that runs AI locally on my PC.

The command to install wsl is shown bellow. It installs Ubuntu by default.

  "wsl --install"
  
The command should be entered in windows command prompt.

**All the commads are entered in Windows WSL Feature from this point forward**
After you have a wsl version running you need to install the linux version of Ollama. You also need to download an AI that you will be using such as llama3.3 in the given example. Ollama's website is "https://ollama.com/"

  "curl -fsSL https://ollama.com/install.sh | sh"
  
   "ollam pull llama3.3"
   
This is a website that lists their current models -> https://ollama.com/search

The next steps are to download Open WebUI
In order to run Open WebUI you need to run a docker container
To install docker enter the following commands or follow the steps on their website -> https://docs.docker.com/engine/install/ubuntu/

  "$ curl -fsSL https://get.docker.com/ | sh"


Now that docker is installed, you can install Open WebUI
To install Open WebUI in a docker contain follow these steps

  "sudo docker pull ghcr.io/open-webui/open-webui:main"
  
  "sudo docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main"

That is it.
If you need troubleshooting help I used these websites,
  https://github.com/open-webui/open-webui#troubleshooting and https://docs.openwebui.com/

To use Open WebUI type "localhost:8080" in you browser
A chat-gpt like page should pop up with the downloaded AI models from Ollama
