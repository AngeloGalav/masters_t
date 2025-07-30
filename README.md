# masters_t
This repository contains the LaTeX source files for a master's thesis on "Optimizing Small Language Models: An Experimental Investigation in Compressing Distilled LLaMA Architectures" focusing on applying and evaluating combinations of memory-efficient optimization techniques on LLMs for edge deployment.

You can find the actual project related to this thesis in [this repo](https://github.com/AngeloGalav/compressed-llama).

## Abstract

Large Language Models have transformed our interaction with technology, yet their massive scale introduces major drawbacks. Their substantial energy consumption and water usage create environmental pressures, while cloud-based architectures limit user autonomy and enable pervasive data collection. Additionally, their resource-intensive nature leads to entirely different challenges for edge deployment, where memory constraints and computational limitations make standard LLMs impractical.

This thesis presents a comprehensive compression pipeline that systematically applies multiple optimization strategies to the compact LLaMA 3.2 1B Instruct model: depth pruning removes redundant transformer layers based on importance metrics, width pruning applies structured sparsity to attention matrices using the WANDA algorithm, Low-Rank Adaptation recovers performance while enabling task-specific fine-tuning, 4-bit quantization further reduces memory footprint through GPTQ, and Eigenspace Low-Rank Approximation provides training-free accuracy recovery.

The experimental evaluation demonstrates that integrating multiple optimization techniques can significantly decrease memory footprint while preserving core language functionality. LoRA adaptation proves particularly effective at recovering capabilities lost during aggressive pruning. However, compression beyond specific thresholds leads to rapid performance deterioration that recovery procedures cannot fully mitigate, revealing fundamental architectural limits in transformer compression.

## Repository Structure

### Main Thesis
The document is structured across five chapters:

- **Chapter 1: Introduction** - Examines the environmental and social impacts of large-scale language models, establishing the motivations and objectives for this research.

- **Chapter 2: Background and Related Work** - Provides technical background on language model evolution from RNNs to Transformers. It also introduces the LLaMA model family and discusses the representative target hardware constraints.

- **Chapter 3: Methodology** - Presents the five-stage compression pipeline that was developed, which includes depth pruning, width pruning (WANDA), LoRA adaptation, quantization (GPTQ), and EoRA compensation, along with the evaluation framework.

- **Chapter 4: Results and Analysis** - Analyzes experimental results across different compression configurations in an ablation study, examining both pruning-only and complete pipeline performance, and identifying optimal trade-offs and performance thresholds.

- **Chapter 5: Conclusions** - Summarizes findings, discusses limitations, and outlines future research directions.

### Presentation
The compiled LaTeX Beamer PDF for the thesis presentation slides are located in the `presentation/` folder.

## Building
To compile the thesis, use your preferred LaTeX compiler with the main document file. The project uses standard LaTeX packages and should compile with most modern LaTeX distributions.


## Main References

* Arpan Suravi Prasad, Moritz Scherer, Francesco Conti, Davide Rossi, Alfio Di Mauro, Manuel Eggimann, Jorge Tómas Gómez, Ziyun Li, Syed Shakib Sarwar, Zhao Wang, Barbara De Salvo, Luca Benini, *Siracusa: A 16 nm Heterogenous RISC-V SoC for Extended Reality with At-MRAM Neural Engine*, 2023. arXiv: 2312.14750. URL: https://arxiv.org/abs/2312.14750

* Bo-Kyeong Kim, Geonmin Kim, Tae-Ho Kim, Thibault Castells, Shinkook Choi, Junho Shin, Hyoung-Kyu Song, *Shortened LLaMA: Depth Pruning for Large Language Models with Comparison of Retraining Methods*, 2024. arXiv: 2402.02834. URL: https://arxiv.org/abs/2402.02834

* Mingjie Sun, Zhuang Liu, Anna Bair, J. Zico Kolter, *A Simple and Effective Pruning Approach for Large Language Models*, 2023. arXiv: 2306.11695. URL: https://arxiv.org/abs/2306.11695

* Elias Frantar, Saleh Ashkboos, Torsten Hoefler, Dan Alistarh, *GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers*, 2022. arXiv: 2210.17323. URL: https://arxiv.org/abs/2210.17323

* Edward J. Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, Weizhu Chen, *LoRA: Low-Rank Adaptation of Large Language Models*, 2021. arXiv: 2106.09685. URL: https://arxiv.org/abs/2106.09685

* Shih-Yang Liu, Maksim Khadkevich, Nai Chit Fung, Charbel Sakr, Chao-Han Huck Yang, Chien-Yi Wang, Saurav Muralidharan, Hongxu Yin, Kwang-Ting Cheng, Jan Kautz, Yu-Chiang Frank Wang, Pavlo Molchanov, Min-Hung Chen, *EoRA: Fine-tuning-free Compensation for Compressed LLM with Eigenspace Low-Rank Approximation*, 2024. arXiv: 2410.21271. URL: https://arxiv.org/abs/2410.21271

* Llama Team, AI @ Meta, *Llama-3.2-1B*, Hugging Face Model, 2024. URL: https://huggingface.co/meta-llama/Llama-3.2-1B