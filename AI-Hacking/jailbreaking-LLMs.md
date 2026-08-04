## Set up OBLITERATUS
```bash
> sudo apt update
> sudo apt install -y python3 python3-pip python3-venv git
> git clone https://github.com/elder-plinius/OBLITERATUS.git
> cd OBLITERATUS
> python3 -m venv venv
> source venv/bin/activate
> pip install --upgrade pip
> pip install -e .
```
- To jailbreak for example Qwen 2.5-0.5B-Instruct,I'll go with the advanced method.But if you see the model misbehaving you can escalate to nuclear.

```bash
obliteratus obliterate Qwen/Qwen2.5-0.5B-Instruct --device cpu --method advanced --output-dir ./abliterated-qwen-0.5b
```
- Once the model downloads, the tool starts running prompts designed to lift the guardrails.
-  The full list of prompts is located in obliteratus/prompts.py.
- I want to run it locally so I'm going to have to setup ollama.
## Setup Ollama
```bash
> git clone https://github.com/ggerganov/llama.cpp
> cd llama.cpp; python3 -m venv venv; source venv/bin/activate
> pip install -r requirements.txt
> python convert_hf_to_gguf.py /home/kali/OBLITERATUS/abliterated-qwen-0.5b --outfile qwen2.5-0.5b-abliterated-f16.gguf --outtype f16
```
- create a Modelfile that points to the model:
```bash
cat > Modelfile << EOF
FROM ./qwen2.5-0.5b-abliterated-f16.gguf
EOF
```
- create the model using Ollama:
```bash
ollama create qwen05b-abliterated -f Modelfile
```
- test it
```bash
ollama run qwen05-abliterated
```