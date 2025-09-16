# Identifying Aspects in Peer Reviews

> **Abstract:** Peer review is central to academic publishing, but the growing volume of submissions is straining the process. This motivates the development of computational approaches to support peer review. While each review is tailored to a specific paper, reviewers often make assessments according to certain *aspects* such as Novelty, which reflect the values of the research community. This alignment creates opportunities for standardizing the reviewing process, improving quality control, and enabling computational support. While prior work has demonstrated the potential of aspect analysis for peer review assistance, the notion of aspect remains poorly formalized. Existing approaches often derive aspects from review forms and guidelines, yet data-driven methods for aspect identification are underexplored. To address this gap, our work takes a bottom-up approach: we propose an operational definition of aspect and develop a data-driven schema for deriving aspects from a corpus of peer reviews. We introduce a dataset of peer reviews augmented with aspects and show how it can be used for community-level review analysis. We further show how the choice of aspects can impact downstream applications, such as LLM-generated review detection. Our results lay a foundation for a principled and data-driven investigation of review aspects, and pave the path for new applications of NLP to support peer review.

Contact person: LU Sheng

https://www.ukp.tu-darmstadt.de/

https://www.tu-darmstadt.de/

##

**Note:** The files in this repository are largely aligned with the sections of the paper, so you can simply locate the corresponding file based on the section of interest. The `ipynb` notebook files additionally contain detailed explanations of the code for easier reproduction and understanding.

## Aspect set construction

### Aspect identification
* Implementation: [notebook-azure.ipynb](notebook-azure.ipynb)
* Pre- and postprocessing: [notebook-processs.ipynb](notebook-processs.ipynb)
* Raw GPT-4o identification results: [annotation - llm.csv](annotation-llm.csv)

### Aspect taxonomy
* Coarsed-grained: [aspects - coarse.csv](aspects-coarse.csv)
* Fine-grained: [aspects - fine.csv](aspects-fine.csv)

### Validity check
* LLM annotation consistency: [notebook-validity_check_&_aspect_analysis.ipynb](notebook-validity_check_&_aspect_analysis.ipynb)
* Annotation guidelines: [annotation-guidelines.pdf](annotation-guidelines.pdf)
* Human annotations: [human_annotations/](human_annotations)

### Data sources
* Raw review data from Openreview (obtained via their API): [data/](./data)
* Selected papers: [selected_papers/](./selected_papers)
* Preprocessed data (segmented into sentences): [preprocessed/](preprocessed)

## Aspect prediction

### Bag-of-Words
* Paper aspect prediction: [notebook-bow-paper_aspect_prediction.ipynb](notebook-bow-paper_aspect_prediction.ipynb)
* Review aspect prediction: [notebook-bow-review_aspect_prediction.ipynb](notebook-bow-review_aspect_prediction.ipynb)

### BERT-based models
* Paper aspect prediction: [bert-paper_aspect_prediction_training.py](bert-paper_aspect_prediction_training.py)
* Review aspect prediction: [bert-review_aspect_prediction_training.py](bert-review_aspect_prediction_training.py)

### GPT-4o
* Implementation: [notebook-azure.ipynb](notebook-azure.ipynb)

### Evaluation scores
* Paper aspect prediction: [evaluation_scores-paper_aspect_prediction.txt](evaluation_scores-paper_aspect_prediction.txt)
* Review aspect prediction: [evaluation_scores-review_aspect_prediction.txt](evaluation_scores-review_aspect_prediction.txt)

## Practical applications

### Aspect analysis
* Implementation: [notebook-validity_check_&_aspect_analysis.ipynb](notebook-validity_check_&_aspect_analysis.ipynb)

### Review comparison and LLM-generated review detection
* Implementation: [notebook-review_comparison_&_detection.ipynb](notebook-review_comparison_&_detection.ipynb)

## Citation
Please use the following citation:

```
@misc{lu2025identifyingaspectspeerreviews,
      title={Identifying Aspects in Peer Reviews}, 
      author={Sheng Lu and Ilia Kuznetsov and Iryna Gurevych},
      year={2025},
      eprint={2504.06910},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2504.06910}, 
}
```

## Disclaimer
This repository contains experimental software and is published for the sole purpose of giving additional background details on the respective publication.
