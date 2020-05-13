# HuggingTweets

*Tweet Generation with Huggingface*

Disclaimer: this demo is not to be used to publish any false generated information but to perform research on Natural Language Generation (NLG).

## Introduction

This project fine-tunes a pre-trained transformer on a user's tweets using [HuggingFace](https://huggingface.co/).

Training and results are logged on [W&B](https://docs.wandb.com/huggingface) (which is integrated in HuggingFace).

![Huggingface + W&B](https://i.imgur.com/vnejHGh.png)

## Usage

1. Install dependencies through `requirements.txt`, `Pipfile` or manually.
2. Run one of the notebooks (I like to use Jupyter Lab):

    a. If you want to understand all the details and control how to fine-tune your model for best results, use `huggingtweets.ipynb`.

    b. If you just want a quick demo, use below link or open `huggingtweets-quick_demo.ipynb` locally

    [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/borisdayma/huggingtweets/blob/master/huggingtweets-quick_demo.ipynb)

## Results

My favorite sample is definitely on Andrej Karpathy, start of sentence "I don't like":

> I don't like this :) 9:20am: Forget this little low code and preprocessor optimization. Even if it's neat, for top-level projects. 9:27am: Other useful code examples? It's not kind of best code, :) 9:37am: Python drawing bug like crazy, restarts regular web browsing ;) 9:46am: Okay, I don't mind. Maybe I should try that out! I'll investigate it :) 10:00am: I think I should try Shigemitsu's imgur page. Or the minimalist website if you're after 10/10 results :) Also maybe Google ImageNet on "Yelp" instead :) 10:05am: Looking forward to watching it talk!

I had a lot of fun running predictions on other people too!

### [See the live report → ](https://app.wandb.ai/borisd13/huggingface-twitter?workspace=user-borisd13)

Quick notes:

* we can get pretty impressive results on very tiny datasets (100 kB) ;
* predictions are definitely better the more data we have (too bad we're limited to only 3200 tweets) ;
* if you don't have enough data just try a few different seeds to see if you get something interesting ;
* I thought it would mainly memorize tweets but there's definitely creativity.

Please try it and share your experiments!

## Future research

Lot more research to do:

* test training top layers vs bottom layers to see how it affects learning of lexical field (subject of content) vs word predictions, memorization vs creativity ;
* losses are not the same based on people (Karpathy is the hardest to predict) ;
* data pre-processing can be optimized (padding, end tokens…) ;
* I could augment text data ;
* do I keep `@` handles or better to use names ;
* what about hashtags? #ConvNets #iloveGANs ;
* need to test more models and do some fine-tuning ;
* pre-train on large Twitter dataset of many people on fine-tune on single user!
