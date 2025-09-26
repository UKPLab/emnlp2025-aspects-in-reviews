The structure of the data in this folder is as follows:

```text
root
└── paper_id (e.g., "WxxYSpsv97")
    ├── Id                  # unique identifier of the paper
    ├── Title               # title of the paper
    ├── Submission_Type     # type of submission (e.g., Regular Short Paper)
    ├── Submission_Track    # track/category of submission (e.g., Question Answering)
    ├── Reviews             # dictionary of reviews, keyed by reviewer_id
    │   ├── review_id (e.g., "LuKErfR4Em")
    │   │   ├── Paper_Topic_and_Main_Contributions  # summary of topic & contributions
    │   │   ├── Reasons_to_accept                   # reasons for acceptance
    │   │   ├── Reasons_to_reject                   # reasons for rejection
    │   │   ├── Soundness                           # reviewer rating: technical soundness
    │   │   ├── Excitement                          # reviewer rating: novelty/excitement
    │   │   └── Reviewer_Confidence                 # reviewer self-assessed confidence
    │   ├── review_id (e.g., "rWsKkyGjcx")
    │   │   └── ... same structure ...
    │   └── review_id (e.g., "DVFOJvJa6W")
    │       └── ... same structure ...
    ├── Meta-review        # summary judgment by meta-reviewer
    └── Decision           # final decision (e.g., Accept, Reject, Accept-Findings)
```

Example:

```
{
    "WxxYSpsv97": {
        "Id": "WxxYSpsv97",
        "Title": "Generating Extractive Answers: Gated Recurrent Memory Reader for Conversational Question Answering",
        "Submission_Type": "Regular Short Paper",
        "Submission_Track": "Question Answering",
        "Reviews": {
            "LuKErfR4Em": {
                "Paper_Topic_and_Main_Contributions": "The paper prosed to incorporate Gated Recurrent Memory with traditional extractive MRC models to deal with conversational question answering task. Experiments on CoQA dataset proved the effectiveness and better space occupancy of proposed GRMR model, compared with traditional baselines such as DrQA, SDNet and PGNet.",
                "Reasons_to_accept": "A space-efficient gated memory mechanism to reduce space occupancy.",
                "Reasons_to_reject": "(1) The baselines involved in Table 1 are generally traditional non-LLM baselines before 2020, which are kind of out of date.\n(2) Two LLM-equipped baselines in Table 1 are FlowQA (with ELMo) and SDNet (with BERT), which show quite better performance gaps beyond proposed GRMR model. What's more, the authors do not have a clear explanation on the improvement of space cost.",
                "Soundness": "2: Borderline: Some of the main claims/arguments are not sufficiently supported, there are major technical/methodological problems",
                "Excitement": "2: Mediocre: This paper makes marginal contributions (vs non-contemporaneous work), so I would rather not see it in the conference.",
                "Reviewer_Confidence": "4: Quite sure. I tried to check the important points carefully. It's unlikely, though conceivable, that I missed something that should affect my ratings."
            },
            "rWsKkyGjcx": {
                "Paper_Topic_and_Main_Contributions": "Authors present Gated Recurrent Memory Reader (GRMR) which which integrates traditional extractive Machine Reading models into a generalized sequence-to-sequence framework. Authors show they achieve better space usage compared to several other models on CoQA dataset, but reports a wide gap with best performing models.",
                "Reasons_to_accept": "* Use of Gated Recurrent Memory Reader (GRMR) method for CQA seems to save space but w/ drop in F1 compared to best performing methods. ",
                "Reasons_to_reject": "* The F1 Score obtained compared to other models, such as FlowQA and SDNet, on CoQA dataset has a wide gap.\n* The improvement in space with 0-ctx doesn't seem proportionate to trade-off in F1.",
                "Soundness": "4: Strong: This study provides sufficient support for all of its claims/arguments. ",
                "Excitement": "3: Ambivalent: It has merits (e.g., it reports state-of-the-art results, the idea is nice), but there are key weaknesses (e.g., it describes incremental work), and it can significantly benefit from another round of revision. However, I won't object to accepting it if my co-reviewers champion it.",
                "Reviewer_Confidence": "4: Quite sure. I tried to check the important points carefully. It's unlikely, though conceivable, that I missed something that should affect my ratings."
            },
            "DVFOJvJa6W": {
                "Paper_Topic_and_Main_Contributions": "The authors propose a new RNN architecture for Conversational Question Answering tasks. Their model comprises 2 modules, 1) Passage encoder, 2) Question decoder. The question decoder contains a question-passage attention, self-attention, and Gated Memory Layer to encoder sequences of conversational questions in a memory-efficient way. Experiments on CoQA dataset show that their model beats most of the baselines except for models using contextualized embeddings such as Elmo and BERT.",
                "Reasons_to_accept": "- new memory efficient architecture for Conversational QA task",
                "Reasons_to_reject": "- Achieves 10 points less F1 than the standard BERT model architecture. I am assuming that the performance gap will be even higher when using more recent and better-pretrained models such as RoBERTa, GPTs, LLAMAs etc.\n- Lacking memory overhead comparisons between baselines (there should be a table in the appendix at least)",
                "Soundness": "4: Strong: This study provides sufficient support for all of its claims/arguments. ",
                "Excitement": "4: Strong: This paper deepens the understanding of some phenomenon or lowers the barriers to an existing research direction.",
                "Reviewer_Confidence": "5: Positive that my evaluation is correct. I read the paper very carefully and I am very familiar with related work."
            }
        },
        "Meta-review": "3: Sound but not Exciting Enough: Accept to Findings",
        "Decision": "Accept-Findings"
    },
  ...
}
```
