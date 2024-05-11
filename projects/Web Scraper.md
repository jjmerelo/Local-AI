# Use your Local AI to help you scrape websites on the internet

## ScrapeGraphAI
1. Install pre-requisites
```
sudo apt-get -y install libnss3 libnspr4 libgbm1 libasound2
python3 ./get-pip.py
sudo apt install python3-pip
pip install playwright
playwright install
```
3. Install ScrapeGraphAI
```
pip install scrapegraphai
```

4. Scrape a website using a configured model
   
Run it with python
  ```
  python 3
  ```
  ```
  from scrapegraphai.graphs import SmartScraperGraph
  
  graph_config = {
      "llm": {
          "model": "ollama/llama2", # make sure you have the model by running 'ollama pull llama2'
          "temperature": 0,
          "model_tokens": 10000, # how many output tokens
          "format": "json",  # Ollama needs the format to be specified explicitly
          "base_url": "http://localhost:11434",  # set Ollama URL
      },
      "embeddings": {
          "model": "ollama/nomic-embed-text", # make sure you have the model by running 'ollama pull nomic-embed-text'
          "base_url": "http://localhost:11434",  # set Ollama URL
      },
      "verbose": True,
  }
  
  smart_scraper_graph = SmartScraperGraph(
      prompt="List me all the projects with their descriptions",
      # also accepts a string with the already downloaded HTML code
      source="https://perinim.github.io/projects",
      config=graph_config
  )
  
  result = smart_scraper_graph.run()
  print(result)
  ```

![image](https://github.com/jjmerelo/Local-AI/assets/169418683/d2dc175c-dc4b-4ee6-a1dd-39691ffc5e18)


```
from scrapegraphai.graphs import SmartScraperGraph

graph_config = {
    "llm": {
        "model": "ollama/llama2", # make sure you have the model by running 'ollama pull llama2'
        "temperature": 0,
		"model_tokens": 50000, # how many output tokens
        "format": "json",  # Ollama needs the format to be specified explicitly
        "base_url": "http://localhost:11434",  # set Ollama URL
		    },
    "embeddings": {
        "model": "ollama/nomic-embed-text", #m ake sure you have the model by running 'ollama pull nomic-embed-text'
        "base_url": "http://localhost:11434",  # set Ollama URL
    },
    "verbose": True,
}

smart_scraper_graph = SmartScraperGraph(
    prompt="List the title of all playlists in this users profile",
    # also accepts a string with the already downloaded HTML code
    source="https://www.youtube.com/@veritasium/playlists",
    config=graph_config
)

result = smart_scraper_graph.run()
print(result)
```

![image](https://github.com/jjmerelo/Local-AI/assets/169418683/d8f68bf8-cddd-4ec7-81f3-b9d04fb993a6)
