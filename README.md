# INFO7375-mini-assignemnt-local-llm-deployment
## Introduction

This repository contains all the necessary files and instructions for setting up and running the `ollma3` model locally. `ollma3` is designed for [specific model applications or tasks]. This README provides clear instructions on how to set up the environment, configure the model, and execute the scripts included in this repository.

Ollama now runs as a native Windows application, including NVIDIA and AMD Radeon GPU support.
After installing Ollama Windows Preview, Ollama will run in the background and the `ollama` command line is available in `cmd`, `powershell` or your favorite terminal application. As usual the Ollama api will be served on`http://localhost:11434`.

## Setup

### Download Windows preview and install
```
https://ollama.com/download/OllamaSetup.exe
```
## QuickStart

To run and chat with [Llama 3](https://ollama.com/library/llama3):

```
ollama run llama3
```
### Deploy Local server

```
ollama serve
```

## check model list

```
ollama list
```
```
C:\Users\81516>ollama list
NAME            ID              SIZE    MODIFIED
solar:latest    059fdabbe6e6    6.1 GB  13 hours ago
llama3:latest   365c0bd3c000    4.7 GB  13 hours ago
```
### Generate a response

Ollama has a REST API for running and managing models.

```
curl -X POST "http://127.0.0.1:11434/api/generate" -H "Content-Type: application/json" -d "{\"model\": \"llama3\", \"prompt\": \"Why is the sky blue?\", \"stream\": false}"
```

Example answer

```json
{"model":"llama3","created_at":"2024-06-21T19:12:43.5976784Z","response":"The sky appears blue because of a phenomenon called Rayleigh scattering, named after the British physicist Lord Rayleigh, who first described it in the late 19th century.\n\nHere's what happens:\n\n1. **Sunlight**: When sunlight enters Earth's atmosphere, it contains all the colors of the visible spectrum (red, orange, yellow, green, blue, indigo, and violet).\n2. **Molecules**: The atmosphere is made up of tiny molecules of gases like nitrogen (N2) and oxygen (O2). These molecules are much smaller than the wavelength of light.\n3. **Scattering**: When sunlight hits these small molecules, it scatters in all directions. This scattering effect is more pronounced for shorter wavelengths, like blue and violet light.\n4. **Blue dominance**: Because the scattering is more effective for shorter wavelengths, the blue light is scattered more than other colors. This means that our eyes perceive the blue light as dominant, giving the sky its characteristic blue color.\n\nIn simpler terms, the short wavelength of blue light makes it bounce around more in the atmosphere, reaching our eyes and making the sky appear blue. The longer wavelengths of red and orange light, on the other hand, continue to travel in a straight line, reaching our eyes from a more direct path.\n\nSo, there you have it! The science behind why the sky is blue.\n\n(Note: This explanation assumes clear atmospheric conditions. Clouds, dust, and pollutants can affect the apparent color of the sky.)","done":true,"done_reason":"stop","context":[128006,882,128007,271,10445,374,279,13180,6437,30,128009,128006,78191,128007,271,791,13180,8111,6437,1606,315,264,25885,2663,13558,64069,72916,11,7086,1306,279,8013,83323,10425,13558,64069,11,889,1176,7633,433,304,279,3389,220,777,339,9478,382,8586,596,1148,8741,1473,16,13,3146,31192,4238,96618,3277,40120,29933,9420,596,16975,11,433,5727,682,279,8146,315,279,9621,20326,320,1171,11,19087,11,14071,11,6307,11,6437,11,1280,7992,11,323,80836,4390,17,13,3146,44,82206,96618,578,16975,374,1903,709,315,13987,35715,315,45612,1093,47503,320,45,17,8,323,24463,320,46,17,570,4314,35715,527,1790,9333,1109,279,46406,315,3177,627,18,13,3146,3407,31436,96618,3277,40120,13280,1521,2678,35715,11,433,1156,10385,304,682,18445,13,1115,72916,2515,374,810,38617,369,24210,93959,11,1093,6437,323,80836,3177,627,19,13,3146,10544,44592,96618,9393,279,72916,374,810,7524,369,24210,93959,11,279,6437,3177,374,38067,810,1109,1023,8146,13,1115,3445,430,1057,6548,45493,279,6437,3177,439,25462,11,7231,279,13180,1202,29683,6437,1933,382,644,35388,3878,11,279,2875,46406,315,6437,3177,3727,433,34782,2212,810,304,279,16975,11,19261,1057,6548,323,3339,279,13180,5101,6437,13,578,5129,93959,315,2579,323,19087,3177,11,389,279,1023,1450,11,3136,311,5944,304,264,7833,1584,11,19261,1057,6548,505,264,810,2167,1853,382,4516,11,1070,499,617,433,0,578,8198,4920,3249,279,13180,374,6437,382,90489,25,1115,16540,22204,2867,45475,4787,13,15161,82,11,16174,11,323,83661,649,7958,279,10186,1933,315,279,13180,6266,128009],"total_duration":49075940300,"load_duration":3135312700,"prompt_eval_count":16,"prompt_eval_duration":1627186000,"eval_count":301,"eval_duration":44311604000}
```

