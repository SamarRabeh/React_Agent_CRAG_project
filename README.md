This project aims to improve the performance of REACT agents—a prompt engineering approach introduced by Google in 2023 that synergizes reasoning and acting in language models—by integrating the CRAG (Consistency-Ranked Augmented Generation) method.

While REACT agents already outperform standard prompting techniques by interleaving reasoning traces and actions, they still suffer from occasional hallucinations and reasoning inconsistencies, especially in complex or multi-step tasks. To address this, we incorporate CRAG, a technique designed to promote logical consistency across multiple generated trajectories through ranking and selection mechanisms.

By merging the structured decision-making flow of REACT with CRAG’s consistency-aware filtering, the goal is to:

Reduce hallucinations and spurious completions
Improve factual accuracy and logical soundness
Achieve better overall task performance compared to standard Chain-of-Thought (CoT) prompting and vanilla REACT agents
This hybrid pipeline is evaluated on multi-hop question answering and code reasoning benchmarks, where agent reliability and coherence are critical.

## Notebooks

- Exploring_ReAct_on_Langchain.ipynb : testing CoT vs React prompting / manual implementation : understanding the technique.
- hotpotqa_GPT3.ipynb: React technique tested on HotpotQA with GPT-3 as a reference LLM.
- hotpotQA_crag_GPT3.ipynb: React coupled with CRAG technique tested on HotpotQA with GPT-3 as a reference LLM.



## Experiments
As HotpotQA and FEVER have large validation sets, we only run 500 random examples (see notebooks). We find PaLM and GPT-3 are better at different tasks.


|       | HotpotQA (500 random dev, EM) | FEVER (500 random dev, EM) 
|----------------------------|-------------------------------|----------------------------|
| GPT-3 + CRAG (3.5-turbo-instruct) |      25                |        51                  
| GPT-3 (3.5-turbo-instruct)        |     19.2               |       45.4                

## Citation

```bibtex
@inproceedings{yao2023react,
  title = {{ReAct}: Synergizing Reasoning and Acting in Language Models},
  author = {Yao, Shunyu and Zhao, Jeffrey and Yu, Dian and Du, Nan and Shafran, Izhak and Narasimhan, Karthik and Cao, Yuan},
  booktitle = {International Conference on Learning Representations (ICLR) },
  year = {2023},
  html = {https://arxiv.org/abs/2210.03629},
}
```bibtex
@inproceedings{yan2024corrective,
  title={Corrective Retrieval Augmented Generation},
  author={Yan, Shi-Qi and Gu, Jia-Chen and Zhu, Yun and Ling, Zhen-Hua},
  journal={arXiv preprint arXiv:2401.15884},
  year={2024}
}
```
