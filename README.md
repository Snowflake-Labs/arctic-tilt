# Arctic-TILT ❄️

This repository contains the official, vLLM-based (0.8.3) implementation of [**Arctic-TILT**](https://aclanthology.org/2025.acl-industry.20/), a sub-billion parameter model for Document Understanding. It achieves performance comparable to models 1000x its size on industrial document processing tasks.

### Features
* ✅ **High Performance:** State-of-the-art results on 7 diverse Document Understanding benchmarks (MP-DocVQA, Kleister, DUDE, etc.).
* 💰 **Cost-Efficient:** Runs on a single consumer-grade 24GB GPU (e.g., NVIDIA A10, L4, RTX 3090/4090).
* 📄 **Long Context:** Processes visually rich, multi-page documents with up to 400k tokens (approx. 500 pages).
* 🚀 **Fast Inference:** Built on vLLM for optimized, high-throughput serving.
* 📖 **Open Source:** Permissively licensed under Apache 2.0 for research and commercial use.

### Quick Start

You can run inference using the provided example script (`examples/tilt_example.py`). The script processes datasets in the Document Understanding Evaluation (DUE) format.

```bash
# Set the attention backend for vLLM
export VLLM_ATTENTION_BACKEND=XFORMERS

# Run inference on a dataset
python examples/tilt_example.py \
    --model Snowflake/snowflake-arctic-tilt-v1.3 \
    --dataset /path/to/your/due-format-dataset \
    --output-dir ./predictions \
    --gpu-memory-utilization 0.8 \
    --enforce-eager
```

### Citation and Credits
Implemented by Piotr Halama (piotr.halama@snowflake.com). If you use Arctic-TILT in your research, please cite our paper:

```
@inproceedings{borchmann-etal-2025-arctic,
    title = "Arctic-{TILT}. Business Document Understanding at Sub-Billion Scale",
    author = "Borchmann, {\L}ukasz  and
      Pietruszka, Micha{\l}  and
      Ja{\'s}kowski, Wojciech  and
      Jurkiewicz, Dawid  and
      Halama, Piotr  and
      J{\'o}ziak, Pawe{\l}  and
      Garncarek, {\L}ukasz  and
      Liskowski, Pawe{\l}  and
      Szyndler, Karolina  and
      Gretkowski, Andrzej  and
      O{\l}tusek, Julita  and
      Nowakowska, Gabriela  and
      Zaw{\l}ocki, Artur  and
      Duhr, {\L}ukasz  and
      Dyda, Pawe{\l}  and
      Turski, Micha{\l}",
    editor = "Rehm, Georg  and
      Li, Yunyao",
    booktitle = "Proceedings of the 63rd Annual Meeting of the Association for Computational Linguistics (Volume 6: Industry Track)",
    month = jul,
    year = "2025",
    address = "Vienna, Austria",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.acl-industry.20/",
    pages = "264--283",
    ISBN = "979-8-89176-288-6",
    abstract = "The vast portion of workloads employing LLMs involves answering questions grounded on PDF or scanned content. We introduce the Arctic-TILT achieving accuracy on par with models 1000$\times$ its size on these use cases. It can be finetuned and deployed on a single 24GB GPU, lowering operational costs while processing rich documents with up to 400k tokens. The model establishes state-of-the-art results on seven diverse Document Understanding benchmarks, as well as provides reliable confidence scores and quick inference, essential for processing files in large-scale or time-sensitive enterprise environments. We release Arctic-TILT weights and an efficient vLLM-based implementation on a permissive license."
}
```
