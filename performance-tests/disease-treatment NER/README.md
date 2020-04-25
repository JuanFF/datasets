# disease-treatment NER evaluation

This test evaluates the [disease-treatment NER](https://github.com/JuanFF/disease-treatment-NER) performance.

I have manually tested a sample of treatment and disease entities retrieved by the NER algorithm. A retrieved entity is tested **Pass** or **Fail** depending on how good or bad the algorithm performs in understanding natural language.

The sample consists of 831 sentences (535 research paper titles from PubMed, and 296 tweets from healthcare-related users).

In the following Twitter message:

_Thank you for spreading the word about botox as a treatment for bruxism_

The NER output is ```{'treatment': 'botox', 'disease': 'bruxism'}```. Both items were properly labeled, so I assign _Pass_ to both the treatment and the disease. However, the algorithm performs bad in the following case:

_Purkinje neuron degeneration on cerebellar ataxia_

where the output is ```{'treatment': 'Purkinje neuron degeneration', 'disease': 'cerebellar ataxia'}```. Here, the treatment tested Fail but the disease is Pass.

For each test case, a link to the original text source is provided.

# Results

| Item | Pass | Fail  | Score |
| Treatment| 692 | 139 | 0.83 |
| Disease| 802 | 29 | 0.96 |
| NER | 1494| 168 | 0.89 |
