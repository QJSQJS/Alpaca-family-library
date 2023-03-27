# Alpaca-family-library

Summarize all low-cost replication methods for Chatgpt countiously. It is believed that with the improvement of data and model fine-tuning techniques, small models suitable for various segmented fields will continue to emerge and have better performance.

Welcome everyone to provide pull requests, and I will also regularly track the latest developments in this repository！

## What’s Alpaca

Contains:  `Dataset`,`Data Genrating Code`, `Finetune Code`, `Web Demo`, `Benchmark`

Alpaca project aims to build and share an instruction-following LLaMA model. 

- Github Page: https://github.com/tatsu-lab/stanford_alpaca
- Blog Post: https://crfm.stanford.edu/2023/03/13/alpaca.html
- Web Demo: https://crfm.stanford.edu/alpaca/

The repo contains:

- The [52K data](https://github.com/tatsu-lab/stanford_alpaca#data-release) used for fine-tuning the model.
- The code for [generating the data](https://github.com/tatsu-lab/stanford_alpaca#data-generation-process).
- The code for [fine-tuning the model](https://github.com/tatsu-lab/stanford_alpaca#fine-tuning).

![Stanford-Alpaca](./assets/logo.png)

The current Alpaca model is fine-tuned from a 7B LLaMA model [1] on 52K instruction-following data generated by the techniques in the Self-Instruct [2] paper, with some modifications that we discuss in the next section. In a preliminary human evaluation, we found that the Alpaca 7B model behaves similarly to the `text-davinci-003` model on the Self-Instruct instruction-following evaluation suite [2].

[1]: LLaMA: Open and Efficient Foundation Language Models. Hugo Touvron, Thibaut Lavril, Gautier Izacard, Xavier Martinet, Marie-Anne Lachaux, Timothée Lacroix, Baptiste Rozière, Naman Goyal, Eric Hambro, Faisal Azhar, Aurelien Rodriguez, Armand Joulin, Edouard Grave, Guillaume Lample. https://arxiv.org/abs/2302.13971v1

[2]: Self-Instruct: Aligning Language Model with Self Generated Instructions. Yizhong Wang, Yeganeh Kordi, Swaroop Mishra, Alisa Liu, Noah A. Smith, Daniel Khashabi, Hannaneh Hajishirzi. https://arxiv.org/abs/2212.10560

Some applications:

- Cleaned Alpaca Dataset：https://github.com/gururise/AlpacaDataCleaned

  - This repository hosts a cleaned and curated version of a dataset used to train the Alpaca LLM (Large Language Model). The original dataset had several issues that are addressed in this cleaned version.

    

## Other models fine-tuned based on the Alpaca model.

A series of fine-tuned models derived from the Alpaca model. Some of them have publicly available weights, are fine-tuned for specific domains, and have better performance. These types of models are still being continuously developed.

### Alpaca-LoRA: Low-Rank LLaMA Instruct-Tuning

Contains:  `Dataset`, `Data Genrating Code`, `Finetune Code`, `Model Weight`, `LoRA`

- Github Page: https://github.com/tloen/alpaca-lora
- Discord Community: [here](https://discord.gg/prbq284xX5)
- Model: **[here](https://huggingface.co/spaces/tloen/alpaca-lora)**

This repository contains code for reproducing the [Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca) results using [low-rank adaptation (LoRA)](https://arxiv.org/pdf/2106.09685.pdf). Alpaca-LoRA provide an Instruct model of similar quality to `text-davinci-003` that can run [on a Raspberry Pi](https://twitter.com/miolini/status/1634982361757790209) (for research), and the code is easily extended to the `13b`, `30b`, and `65b` models.

In addition to the training code, which runs within five hours on a single RTX 4090, Alpaca-LoRA publish a script for downloading and inference on the foundation model and LoRA, as well as the resulting [LoRA weights themselves](https://huggingface.co/tloen/alpaca-lora-7b/tree/main). To fine-tune cheaply and efficiently, Alpaca-LoRA use Hugging Face's [PEFT](https://github.com/huggingface/peft) as well as Tim Dettmers' [bitsandbytes](https://github.com/TimDettmers/bitsandbytes).

Without hyperparameter tuning, the LoRA model produces outputs comparable to the Stanford Alpaca model. 

Some applications:

- Alpaca-LoRA as a Chatbot Service: https://github.com/deep-diver/Alpaca-LoRA-Serve



### Code Alpaca: An Instruction-following LLaMA Model trained on code generation instructions

Contains: `Dataset`, `Data Genrating Code`, `Finetune Code`, `Web Demo`

This is the repo for the Code Alpaca project, which aims to build and share an instruction-following LLaMA model for code generation. This repo is fully based on [Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca) ,and only changes the data used for training. Training approach is the same.

- Github Page: https://github.com/sahil280114/codealpaca
- Web Demo: https://code-alpaca-demo.vercel.app/



### Evolving Alpaca: An Empirical Study on Instruction Tuning for Large Language Models (**Alpaca-CoT**)

Contains: `Dataset`, `Data Genrating Code`, `Finetune Code`, `LoRA`

This is the repository for the `Evolving Alpaca` project, which aims to extensively collect instruction-tuning datasets (especially the CoT datasets) and conduct an in-depth empirical study based on [LLaMA](https://arxiv.org/abs/2302.13971v1) model. `Evolving` is used to describe the continuous expansion of our instruction-tuning data collection, which will continuously enhance [Alpaca](https://github.com/tatsu-lab/stanford_alpaca)'s instruction-following capabilities.

- Github Page: https://github.com/PhoebusSi/Alpaca-CoT
- Web Demo: https://code-alpaca-demo.vercel.app/

![Alpaca-CoT](./assets/Alpaca-CoT-2.jpg)



### 骆驼(Luotuo): Chinese-alpaca-lora

Contains: `Data Genrating Code`,  `Model Weight`, `LoRA`, `Benchmark`

A Chinese finetuned instruction LLaMA. 

- Github Page: https://github.com/LC1332/Chinese-alpaca-lora
- Model: https://huggingface.co/silk-road/luotuo-lora-7b-0.3

<img src="./assets/camel_back.png" alt="img" style="zoom:67%;" />



### KoAlpaca: Korean Alpaca Model based on Stanford Alpaca

Contains:  `Dataset`, `Data Genrating Code`, `Finetune Code`, `Model Weight`, `LoRA`, `Benchmark`

The Korean Alpaca model is learned in the same way as the Stanford Alpaca model.

Benchmark

- Github Page: https://github.com/Beomi/KoAlpaca
- Telegram app: http://pf.kakao.com/_wdRxcxj
- Model: https://huggingface.co/beomi/KoAlpaca-65B-LoRA

<img src="./assets/KoAlpaca-20230327220706243.png" alt="KoAlpaca icon" style="zoom:33%;" />



## Other Chatgpt Reproduction Models

### ChatGLM-6B

Contains:   `Model Weight`, `Web Demo`

- Github Page: https://github.com/THUDM/ChatGLM-6B
- Blog: https://chatglm.cn/blog
- Model: [Hugging Face Hub](https://huggingface.co/THUDM/chatglm-6b)

ChatGLM-6B is an open-source, bilingual (Chinese and English) conversational language model based on the General Language Model (GLM) architecture with 6.2 billion parameters. With model quantization technology, users can deploy it locally on consumer-grade graphics cards (with a minimum of only 6GB VRAM at INT4 quantization level). ChatGLM-6B uses similar techniques to ChatGPT and has been optimized for Chinese question answering and dialogue. After training on approximately 1 trillion identifiers in both Chinese and English, combined with supervised fine-tuning, feedback self-help, human feedback reinforcement learning technologies, the 62 billion parameter ChatGLM-6B can generate responses that are quite consistent with human preferences.

Some applications:

- A cost-effective implementation plan for ChatGPT, based on Tsinghua's ChatGLM-6B + LoRA for finetuning: https://github.com/mymusise/ChatGLM-Tuning
- *Chatglm* 6b finetuning and alpaca finetuning: https://github.com/ssbuild/chatglm_finetuning
- A webui for ChatGLM made by THUDM.https://github.com/Akegarasu/ChatGLM-webui