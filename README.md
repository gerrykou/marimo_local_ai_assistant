# marimo local ai assistant

## Install dependencies

### Install and run with uv
Initiate the uv project:
```
uv init
```
or if you want to select a specific python version:
```
uv venv --python 3.13
uv init
```
Then, install dependencies and run marimo:
```
uv add marimo openai
uv run marimo edit
```
### Or install and run with pip
```
python -m venv .venv
source .venv/bin/activate
pip install marimo openai
marimo edit
```
## Run LLM model locally with docker
Get started with docker model runner here:  
https://docs.docker.com/ai/model-runner/get-started/
```
docker model list
docker model run qwen2.5
```

### Test your local LLM is running
http://localhost:12434/engines/llama.cpp/v1/
```
curl http://localhost:12434/engines/llama.cpp/v1/chat/completions \
    -H "Content-Type: application/json" \
    -d '{
        "model": "ai/qwen2.5",
        "messages": [
            {
                "role": "system",
                "content": "You are a helpful assistant."
            },
            {
                "role": "user",
                "content": "Write 20 words on docker model runner"
            }
        ]
    }'
```

Check this video to learn more about docker model runner:  
https://www.youtube.com/watch?v=KL4WU_04CrA

Here the docker model runner REST API documentation:  
https://docs.docker.com/ai/model-runner/api-reference/#available-openai-endpoints

## Setup marimo AI assistant
* Open marimo settings
* Go to `AI Providers` tab
    * expand Ollama and paste:  
    http://localhost:12434/engines/llama.cpp/v1/models
* Go to `AI Models` tab
    * Click `Add Model`
    * For `Provider` select from the dropdown menu: `Ollama`
    * For the Model paste: ai/qwen2.5
    * Click `Add`
    * Enable the Model from Ollama
* Go to `AI Features` tab
    * select the model: `Ollama` -> `ai/qwen2.5`

Setup video here:  
https://www.youtube.com/watch?v=fexJ4ghJaKo

How to use the AI assistant in marimo:  
https://www.youtube.com/watch?v=gEbruDWcSsM

## Run LLM model locally with ollama
If you run your model locally with Ollama, check the documentation here:  
https://docs.ollama.com/api/introduction  

The model is running in `:11434`  
http://localhost:11434/api
