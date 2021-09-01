# Fine-tune and host Hugging Face BERT models on Amazon SageMaker

***This is the code repository for: https://aws.amazon.com/blogs/machine-learning/fine-tune-and-host-hugging-face-bert-models-on-amazon-sagemaker/***

The last few years have seen the rise of transformer deep learning architectures to build natural language processing (NLP) model families. The adaptations of the transformer architecture in models such as BERT, RoBERTa, T5, GPT-2, and DistilBERT outperform previous NLP models on a wide range of tasks, such as text classification, question answering, summarization, and text generation. These models are exponentially growing larger in size from several million parameters to several hundred billion parameters. As the number of model parameters increases, so does the computational infrastructure that is necessary to train these models.
This requires a significant amount of time, skill, and compute resources to train and optimize the models.
Unfortunately, this complexity prevents most organizations from using these models effectively, if at all. Wouldn’t it be more productive if you could just start from a pre-trained version and put them to work immediately? This would also allow you to spend more time on solving your business problems.

**This notebook shows you how to use Amazon SageMaker and Hugging Face to fine-tune a pre-trained BERT model and deploy it as a managed inference endpoint on SageMaker.**

We're using an offshoot of [BERT](https://arxiv.org/abs/1810.04805) called [DistilBERT](https://arxiv.org/abs/1910.01108) that is smaller, and so faster and cheaper for both training and inference. A pre-trained model is available in the [`transformers`](https://huggingface.co/transformers/) library from [Hugging Face](https://huggingface.co/).

The [Amazon Reviews Polarity dataset](https://github.com/dsk78/Text-Classification---Amazon-Reviews-Polarity) consists of reviews from Amazon. The data span a period of 18 years, including ~35 million reviews up to March 2013. Reviews include product and user information, ratings, and a plaintext review. It's avalaible under the [`amazon_polarity`](https://huggingface.co/datasets/amazon_polarity) dataset on [Hugging Face](https://huggingface.co/).
