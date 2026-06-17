# Much Ado About Accessibility: Exploration of Online Information Access Systems' Responses to Autistic Users

## Abstract

Autism Spectrum Disorder is a neuro-developmental condition that may affect the way a person learns, behaves, and interacts with their environment. Autistic individuals are known to often rely on mainstream information access systems, such as search engines, as their initial point for information discovery. Despite their active online information-seeking practices, autistic individuals struggle to extract information from the resources they encounter, leading to frustration. This raises the question of whether these systems fit the needs and expectations of this population. In this work, we empirically explore how different mainstream information access systems respond to autistic users’ inquiries through the lens of web content accessibility. Specifically, we focus on three text-based perspectives known to impact autistic individuals’ information seeking – structure, readability, and concreteness (tangibility of terminology) of web content. For our analysis, we leverage established accessibility guidelines for autistic individuals to create accessibility profiles for Google, Bing, ChatGPT, and Gemini, providing an overview of various aspects of each system’s responses to common inquiries of autistic individuals. Given the influence of query formulation on produced responses, we also investigate the impact of explicitly informing the system of the user’s condition on the accessibility profile of the considered systems. Our findings reveal potential accessibility limitations of mainstream information access systems when responding to autistic users’ inquiries, more so if their information need is related to the searchers’ condition. Furthermore, including a diagnosis-disclosing phrase in autistic users’ inquiries results in responses that are even less accessible to autistic individuals. Based on our findings, we reflect on autistic users’ access to information and the role of information access technologies in supporting their information-seeking process.

## Citation
Please use the following reference when citing this repository in your work:
```
@article{Chakrabarti_Pera_2026,
    author={Chakrabarti, Hrishita and Pera, Maria Soledad},
    title={Much Ado about Accessibility: An Exploration of Online Content Accessibility from an Autism-Informed Perspective},
    journal={Information Retrieval Research},
    volume={2},
    number={1},
    year={2026},
    pages={59–112},
    url={https://irrj.org/article/view/25297},
    DOI={10.54195/irrj.25297}
}
```

## Reproducibility Code

## User Queries
Refer to `Data/query_example_file.xlsx` for an example file for user queries. The excel file contains the following coloumns:

1. query: The query that captures an information need of a user
2. ngram: The ngram length of the query
3. domain_relevant: TRUE if query related to ASD, FALSE otherwise (**Note:** this column is applicable only for files containing autistic users' inquiries.)

## Synthetic Log Generation

### Step 1: Accessing API endpoints
We rely on official API endpoints to elicit responses from Google, Bing, ChatGPT, and Gemini. Each API endpoint requires an access token which is stored in `Code/API_keys.json` at the time of execution. 

Personal access tokens can be generated using the documentations linked below.

1. [Google Custom Search JSON API](https://developers.google.com/custom-search/v1/introduction#identify_your_application_to_google_with_api_key)
2. [Bing Web Search API](https://learn.microsoft.com/en-us/bing/search-apis/bing-web-search/create-bing-search-service-resource)
3. [OpenAI API](https://platform.openai.com/api-keys)
4. [Gemini API](https://ai.google.dev/gemini-api/docs/api-key)

**Note: Access tokens are meant to be private and it is strongly advised to remove the access token strings from the JSON file prior to sharing the code base publically to avoid any data leakage issues.**

### Step 2: Generating IAS responses

In the first code block in `Code/API_calls.ipynb`, assign the variables `target_og_query_file_path`, `target_rephrased_query_file_path`, and `control_query_file_path` the names of the file containing the autistic user queries, rephrased autistic user queries, and control group queries respectively and then run all all the code blocks in `Code/API_calls.ipynb` one after the other. 

After all code blocks have run successfully, the `Data/` folder should be populated with excel files corresponding to the responses elicited from Google, Bing, ChatGPT, and Gemini, respectively.

## Accessibility analysis
To create the accessibility profiles of each IAS run the code blocks in `Code/accessibility_analysis.ipynb` in order. To compare the generated accessibility profiles run the code blocks in `Code/stats_computation.ipynb` in order.
