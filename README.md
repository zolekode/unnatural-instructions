# Unnatural Instructions

This repository contains the Unnatural Instructions dataset. Unnatural Instructions is a dataset of instructions automatically generated by a Large Language model.
See full details in the paper: "[Unnatural Instructions: Tuning Language Models with (Almost) No Human Labor](https://arxiv.org/abs/2212.09689)"

## 🗃️ Content
The `data` folder contains two files: `core_data.jsonl`, containing the Unnatural Instructions core dataset of 68,478 instruction-input-output triplets, and `full_data.jsonl`, containing the full 240,670 Unnatural Instructions examples. The full data was constructed by expanding the core data with automatically generated instruction paraphrases.

## 📄 Format
### Core data
Each line in `core_data.jsonl` is a JSON object with two fields - `instruction`, which is a natural language instruction describing a task, and `instances`, an array of JSON objects, each contains
- `input`: An input for the task described by the `instruction`
- `instruction_with_input`: The instruction concatenated with the `input`
- `constraints`: The task's output space constraints
- `output`: The output of executing `instruction` with the given `input`

### Full data
`core_data.jsonl` has the same structure as `core_data.jsonl`, but with one additional field - `reformulations`. `reformulations` is an array of JSON objects, each corresponds to an automatically generated paraphrase for the given instruction. The structure of each JSON object is identical to the one described above for `instances`.

## 📘 Citation
If you make use of Unnatural Instructions, please cite the following paper:
```
@misc{honovich2022unnatural,
      title = {Unnatural Instructions: Tuning Language Models with (Almost) No Human Labor},
      author = {Honovich, Or and Scialom, Thomas and Levy, Omer and Schick, Timo},
      url = {https://arxiv.org/abs/2212.09689},
      publisher = {arXiv},
      year={2022}
}
```
