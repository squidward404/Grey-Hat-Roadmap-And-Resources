## Searching vulnerable servers
- On `shodan` search `Ollama`

## Testing 
- To see which models are running(choose ones that are not in the cloud)

```bash
curl -s http://IP:11434/api/tags | jq -r '.models[].name'
 ```

- To test if a specific model is live

```bash
curl -s http://IP:11434/api/generate \
  -d '{
    "model": "hf.co/huihui-ai/Huihui-Qwythos-9B-Claude-Mythos-5-1M-abliterated-GGUF:latest",
    "prompt": "Reply with only: alive",
    "stream": false
  }' | jq
  ```
## Download pentestcode
- run:
```bash
wget https://github.com/s0ld13rr/pentestcode/releases/download/v0.2.3/pentestcode-linux-x64.tar.gz
```
```bash
7z x pentestcode-linux-x64.tar.gz
```
```bash
7z x pentestcode-linux-x64.tar
```
## Edit config file
- The config file is at `~/.config/pentestcode/pentestcode.json`
```bash
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "ollama": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "Remote Ollama",
      "options": {
        "baseURL": "http://IP:11434/v1"
      },
      "models": {
        "llama3.1:8b": {
          "name": "Llama 3.1 8B"
        }
      }
    }
  },
  "model": "ollama/llama3.1:8b"
}
```
