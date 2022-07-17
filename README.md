# Motivation
Generative language models are awesome! The rapid advances of this technology in the last few years can only be described as breathtaking ([Min et al., 2021](https://arxiv.org/pdf/2111.01243.pdf); [Tang, Guerin, Li & Lin, 2022)](https://arxiv.org/pdf/2203.03047.pdf). Such models are already showing an impressive proficiency for tasks as complex and multi-facetted as storytelling ([Alhussain & Azmi, 2021)](https://www.researchgate.net/profile/Aqil-Azmi/publication/351858590_Automatic_Story_Generation_A_Survey_of_Approaches/links/60afe2e0299bf13438efd3bc/Automatic-Story-Generation-A-Survey-of-Approaches.pdf). If you somehow find yourself reading this without having experienced the power and beauty of generative language models, I urge you to try out one of the many available resources:
* [Novel AI](https://novelai.net/#/) is a _"monthly subscription service for AI-assisted authorship [and] storytelling"_, based on open-source language models (they have a free trial)
* GooseAI, a _"NLP-as-a-Service delivered via API"_, offers a [playground to try many open-source language models with a $10 trial](https://goose.ai/playground).
* [KoboldAI](https://github.com/KoboldAI/KoboldAI-Client) offers an interface for hosting your model locally or on Google colab (setting it up is non-trivial, though)

As impressive as the existing implementations are, I believe that the methods for evaluating stories generated by language models are lacking a way to reliably appraise output for aspects that human readers actually care about. This makes it hard to understand how different models and generation settings differ in the quality and nature of their generated stories. The AI Story Scale aims to solve this problem by providing researchers and practitioners with a solid foundation for measuring the quality and nature of an AI-generated stories.

In short, the AI Story Scale measures five aspects…

## Current Story Quality Measures
Before diving into the details of what constitutes the AI Story Scale, let's quickly run through the current approaches to evaluate a story generated by a generative model. I will also try to lay out why I think researchers could profit from the addition of the AI Story Scale to the arsenal of evaluation metrics.

### Measures Based On A Ground Truth
Measures such as perplexity ([Jelinek et al. 1977](https://link.springer.com/article/10.1007/s10579-005-2693-4)) or BLEU ([Papineni et al. 2002](https://aclanthology.org/P02-1040.pdf)) compare output against a previously established 'correct' answer (e.g., probability to reproduce sentences from a test dataset or word overlap with a target sentence). While useful to measure the fit of the generated story against a gold standard, they don't directly access the story's general properties independent of an a priori test set. Since one of the most exciting applications of GLMs is their potential for the creative generation of novel stories, it seems important to also create a way to evaluate these stories in a more general sense.

### Measures Based On Human Evaluation
A different approach is to use human judges to evaluate a story ([Purdy et al., 2018](https://www.aaai.org/ocs/index.php/AIIDE/AIIDE18/paper/viewFile/18106/17228); [Yao et al., 2019](https://ojs.aaai.org/index.php/AAAI/article/view/4726/4604);  [Castricato et al., 2021a](https://arxiv.org/pdf/2104.07472.pdf); [Castricato et al., 2021b](https://par.nsf.gov/servlets/purl/10249509); [Callan & Foster, 2021](http://ceur-ws.org/Vol-3105/paper9.pdf)). After all, the end goal of story generation by language models is to produce convincing and engaging stories that people like to read and enjoy. Is it not natural then to use humans as our ultimate measure of story quality?

Ultimately, I believe that human evaluation of AI-generated stories deserves serious attention. It could be used to not only measure the 'overall quality' of stories, but also to help understand what kind of stories different models are likely to produce and how they differ. It could also be used to explore how story quality changes across generations or as we tweak a model's architecture or hyperparameters.

The existing measures represent an important first step for capturing how humans experience stories written by language models. However, I think it could benefit from being further refined and extended. But let's not get ahead of ourselves. Before we review existing instruments for human evaluation, it might be good to establish what we would actually want from a scale for valid and reliable measurements.

## How Do You Measure Opinions, Anyway?
As it turns out, measuring anything from pesky humans is messy. Especially when it comes to internal states. By internal states, I mean of the human experience that are not _directly_ accessible by observation. These are strange things like mood, opinions, attitudes, beliefs, or preferences. To make it sound even more complicated than it already is, psychologists call these things 'latent constructs' (or just 'constructs') or 'latent variables'. Latent variables are not directly observable, but have to be inferred from other observations – like what option someone picks on a question like "On a scale from 1 to 5, how interesting is this story?".

One might think that the way we measure these variables would be straightforward: We want to know how interesting the story is. So, we just ask a person how interesting they found the story and then average that across all participants. Done, let's move on!

However, measuring latent variables comes with its own unique challenges. Challenges that researchers not familiar with the peculiarities of measuring internal states might be unaware of. However, ignore these issue at your own peril! Careless measurement of internal states can lead to very biased and potentially meaningless results.

Luckily, there is a field that has studied this issue for decades: psychometrics. It is a discipline that has developed an array of tools to measure latent constructs, as well as a rich theory to help understand what kind of errors can occur in these measurements and how to reduce them. I would urge AI researchers to take measuring human evaluations seriously and to take the lessons learned by psychometrics to heart. This way, AI research could profit from decades of hard work by psychologists and statisticians to improve how we measure what matters to humans – like the quality of AI-generated stories.

### Potential Issues In Measuring Latent Constructs
Insights from measurement theory can help us to be cognizant of potential pitfalls when measuring latent constructs. Consider first what is implicitly assumed when we measure something like 'interestingness' by asking "On a scale from 1 to 5, how interesting is this story?":
* We assume that when humans read stories, something like interestingness exists in their mind as a criterion for judging the story (if it does not exist, what are you measuring?).
* Perceived interestingness is abstract and not directly observable. Unfortunately, there is no little sign lightning up after a person reads a story, saying "For me this story has an interestingness of 3.57". However, we believe perceived interestigness can be measured by asking the person appropriate questions about it.
* We assume that when a person answers the question "On a scale from 1 to 5, how interesting is this story?" the perceived interestingness causes at least part of the response.[^1]
     * _Other causes for the response can be considered measuring error. For example, a person might give a higher rating because she is in a good mood, generally gives high ratings on questionnaires, etc…_

[^1]: This is the first footnote.
_Note: This model of measurement is known as the reflective measurement model: Constructs are assumed to cause indicators (responses to questions). The flip side would be a formative measurement model. However, I consider a reflective measurement model to be more appropriate for the assumptions researchers imply when collecting human evaluations, and will therefore not give further consideration to the formative measurement model._

Problems with this process can arise at different points:
1. Not matter how plausible it sounds in theory, the latent variable might not actually be meaningful for real word measurements (people might not consider 'interestingness' an actual criterion when judging stories).
2. The latent variable is meaningful, but the questions we are using to measure it are not actually measuring it (e.g., our question(s) might measure 'creativity' rather than 'interestingness').
3. The latent variable is meaningful, but the questions we are using to measure are measuring it with a lot of error. The measurements we are getting are so imprecise to be basically useless.

Issue 1) concerns the _underlying factorial structure_ of questions (i.e., the latent factors that are predicting answers to the questions). Issue 2) concerns whether questions measure what they are supposed to measure. This is generally referred to as _validity_. Issue 3) concerns the precision or measurement error of question items. This is also referred to as the _reliability_ of question items. 

to be continued...
