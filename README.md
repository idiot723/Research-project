# Research-project

The project proposes a framework for a multi-dimensional dataset that covers character experiences, interpersonal relationships, and personality traits. It also provides a dataset containing five characters from anime or movies. After fine-tuning and evaluating the GPT-3.5 and Phi-3 models using the project dataset, the models trained with the dataset achieved the highest win rates in evaluations, demonstrating performance that rivals or even surpasses GPT-3.5. In multi-dimensional text evaluations and  personality traits questionnaire evaluations, the fine-tuned models also exhibited strong performance, effectively capturing character traits during role-playing.

You need to replace the `api_key` in the code with your own OpenAI API key. Additionally, due to GitHub's file size upload limit, the fine-tuned Phi-3 pre-trained model has not been uploaded, and due to access restrictions, you will still need to fine-tune the GPT-3.5 model yourself.

Here is the description of each file and folder:
## Files:
### Project code:
**construct.ipynb:** Using to construct datasets

**train.ipynb:** Using for model training

**evaluation.ipynb:** Using for model evaluation

### Datasets:
**big5_dim.json:** A brief introduction to the five dimensions of the Big Five personality traits and the facets associated with each dimension.

**bigfive_questionnaire_eng.json:** Big Five Personality Traits Questionnaire from the [Incharacter](https://github.com/LC1332/Chat-Haruhi-Suzumiya/tree/main/research/personality) Project [1].

**profiles-eng_desc.json:** Character descriptions from [RoleLLM](https://huggingface.co/datasets/ZenMoore/RoleBench) dataset [2].

**profiles-eng_scripts.json:** Character name and corresponding work title from [RoleLLM](https://huggingface.co/datasets/ZenMoore/RoleBench) dataset [2].

**withbig5.json:** The Big 5 personality traits analysis of 95 characters in [RoleLLM](https://huggingface.co/datasets/ZenMoore/RoleBench) dataset [2].

## Folders:
**agnostic:** This folder contains the profile-agnostic questions for each character. 

- Files without the `_factu` suffix are files that contain only the question-answer dictionary.
- Files with the `_factu` suffix also include the factualness of the question in the dictionary.

**based:** This folder contains the profile-agnostic questions for each character. 

- Files without the `_comp` suffix are files that contain only the question-answer dictionary.
- Files with the `_comp` suffix also include the completeness of the question in the dictionary.

**general_q:** This folder contains the general question for each character. 

- Files with the `_origin` suffix contain the question and the answer from the original [RoleLLM](https://huggingface.co/datasets/ZenMoore/RoleBench) dataset (for the two new anime characters, this file contains only the question) [2].
- The file with the `_dic` suffix contains the question and the answer from the Oblivion command.

**profile:** The folder contains the personal profiles of 11 roles as well as the profiles of the important roles associated with them. Only five of these 11 roles constructed a complete dataset.

**question:** This folder contains the character relationship questions. 

- Files without extensions are raw, unprocessed string-format generated results.
- Files with the suffix `_dic` contain processed questions and answers in dictionary format, which will be included in the training set.
- Files with the suffix `_test` are unprocessed generated content that will be used in the test set.

**score:** This folder contains the relationship scores for each character.

**total_q:** This folder contains the training sets for all characters. 

- The file `train_set.json` is combined train set for all five characters.
- The file `gpt_train_set.json` is the training set with questions for five characters used for fine-tuning GPT-3.5.
- The file `converted_dataset.jsonl` is the training set converted into the data format required by OpenAI.

**test_valid:** This folder contains the test and validation sets for each character.

- Files with the suffix `_test` are the test sets.
- Files with the suffix `_valid` are the validation sets.
- The files `test_set.json` and `valid_set.json` are the combined test and validation sets for all five characters.

**result:** 
This folder contains the results of all validation methods. 

- The files with the suffix `_4o` include rankings of different models and prompts evaluated by GPT evaluator (win rate assessment). 
- Files with the suffix `_120` contain a DataFrame with questions, generated results from different models and prompts, and their BERT scores. 
- Files with the suffix `_big5_test` include questions from the Big Five personality traits questionnaire and a DataFrame of results generated by the fine-tuned Phi-3 model. Files with the suffix “_big5” are the DataFrames converted into dictionary format. 
- Files with the suffix `_big5_eval` store the evaluation scores and rationale for the questionnaire responses. Files with the suffix “_dimension_eval” provide scoring and rationale for each result generated by different models and prompts across four dimensions (factual correctness, personality, values, and avoiding hallucination).

[1] Wang, X., Tu, Q., Fei, Y., Leng, Z., & Li, C. (2023). *Does Role-Playing Chatbots Capture the Character Personalities? Assessing Personality Traits for Role-Playing Chatbots*. arXiv preprint arXiv:2310.17976.

[2] Wang, Z. M., Peng, Z., Que, H., Liu, J., Zhou, W., Wu, Y., Guo, H., Gan, R., Ni, Z., Zhang, M., Zhang, Z., Ouyang, W., Xu, K., Chen, W., Fu, J., & Peng, J. (2023). *RoleLLM: Benchmarking, Eliciting, and Enhancing Role-Playing Abilities of Large Language Models*. arXiv preprint arXiv:2310.00746.
