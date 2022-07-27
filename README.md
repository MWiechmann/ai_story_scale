# Summary
Coming soon…

# Motivation
Generative language models (GLMs) are awesome! The rapid advances of this technology in the last few years can only be described as breathtaking ([Min et al., 2021](https://arxiv.org/pdf/2111.01243.pdf); [Tang, Guerin, Li & Lin, 2022)](https://arxiv.org/pdf/2203.03047.pdf). Such models are already showing an impressive proficiency for tasks as complex and multi-facetted as storytelling ([Alhussain & Azmi, 2021)](https://www.researchgate.net/profile/Aqil-Azmi/publication/351858590_Automatic_Story_Generation_A_Survey_of_Approaches/links/60afe2e0299bf13438efd3bc/Automatic-Story-Generation-A-Survey-of-Approaches.pdf). If you somehow find yourself reading this without having experienced the power and beauty of generative language models, I urge you to try out one of the many available resources:
* [Novel AI](https://novelai.net/#/) is a _“a monthly subscription service for AI-assisted authorship, storytelling, virtual companionship, or simply a GPT powered sandbox for your imagination”_, based on open-source language models (they have a free trial)
* [GooseAI](https://goose.ai/playground), a _“NLP-as-a-Service delivered via API”_, offers a playground to try many open-source language models with a $10 trial.
* [KoboldAI](https://github.com/KoboldAI/KoboldAI-Client) offers an interface for hosting your model locally or on Google Colab (setting it up is non-trivial, though)

However, as impressive as the existing implementations are, I believe that the methods for evaluating stories generated by language models are lacking a way to reliably appraise output for aspects that human readers actually care about. This makes it hard to understand how different models and generation settings differ in the quality and nature of their generated stories. The AI Story Scale aims to solve this problem by providing researchers and practitioners with a solid foundation for measuring the quality and nature of AI-generated stories.

I believe that this measure addresses shortcomings of current measures for human story evaluation. Let me try to explain why:

## Current Story Quality Measures
In this section, I will quickly run through the current approaches to evaluate a story generated by a generative model. I will also try to lay out why I think researchers could profit from the addition of the AI Story Scale to the arsenal of evaluation metrics.

### Measures Based On A Ground Truth
Measures such as perplexity ([Jelinek et al. 1977](https://link.springer.com/article/10.1007/s10579-005-2693-4)) or BLEU ([Papineni et al. 2002](https://aclanthology.org/P02-1040.pdf)) compare output against a previously established 'correct' answer (e.g., probability to reproduce sentences from a test dataset or word overlap with a target sentence). While useful to measure the fit of the generated story against a gold standard, they don't directly access the story's general properties independent of an priori test set. Since one of the most exciting applications of GLMs is their potential for the creative generation of novel stories, it seems important to also create a way to evaluate these stories in a more general sense.

### Measures Based On Human Evaluation
A different approach is to use human judges to evaluate a story ([Purdy et al., 2018](https://www.aaai.org/ocs/index.php/AIIDE/AIIDE18/paper/viewFile/18106/17228); [Yao et al., 2019](https://ojs.aaai.org/index.php/AAAI/article/view/4726/4604);  [Castricato et al., 2021a](https://arxiv.org/pdf/2104.07472.pdf); [Castricato et al., 2021b](https://par.nsf.gov/servlets/purl/10249509); [Callan & Foster, 2021](http://ceur-ws.org/Vol-3105/paper9.pdf)). After all, the end goal of story generation by language models is to produce convincing and engaging stories that people like to read and enjoy. Is it not natural then to use humans as our ultimate measure of story quality?

Personally, I believe that human evaluation of AI-generated stories deserves serious attention. It could be used to not only measure the 'overall quality' of stories, but also to help understand what _kind_ of stories different models are likely to produce and how they differ. It could also be used to explore how story quality changes across generations as we tweak a model's architecture or hyperparameters.

The existing measures represent an important first step for capturing how humans experience stories written by language models. However, I think they could benefit from being further refined and extended. But let's not get ahead of ourselves. Before we review existing instruments for human evaluation, it might be good to establish what we would actually want from a scale measuring subjective story experience.

## How Do You Measure Opinions, Anyway?
As it turns out, measuring anything from pesky humans is messy. Especially when it comes to internal states. By internal states, I mean the human experience that are not _directly_ accessible by observation. These are strange things like mood, opinions, attitudes, beliefs, or preferences. To make it sound even more complicated than it already is, psychologists call these things 'latent constructs' (or just 'constructs') or 'latent variables'. Latent variables are not directly observable, but have to be inferred from other observations – for example, what option someone picks on a question like “On a scale from 1 to 5, how interesting is this story?”.

One might think that the way we measure these variables would be straightforward: We want to know how interesting the story is. So, we just ask a person how interesting they found the story and then average that across all participants. Done, let's move on!

However, measuring latent variables comes with its own unique challenges; challenges that researchers not familiar with the peculiarities of measuring internal states might be unaware of. However, ignore these issue at your own peril! _Careless measurement of internal states can lead to very biased and potentially meaningless results!_

Luckily, there is a field that has studied this issue for decades: psychometrics. It is a discipline that has developed an array of tools to measure latent constructs, as well as a rich theory to help understand what kind of errors can occur in these measurements and how to reduce them (for an introduction see [Furr, 2011](https://methods.sagepub.com/book/scale-construction-and-psychometrics-for-social-and-personality-psychology); [El-Den et al., 2020](https://onlinelibrary.wiley.com/doi/pdfdirect/10.1111/ijpp.12600); [Flake & Fried, 2020](https://journals.sagepub.com/doi/full/10.1177/2515245920952393)). I would urge AI researchers to take measuring human evaluations seriously and to take the lessons learned by psychometrics to heart. This way, AI research could profit from decades of hard work by psychologists and statisticians to improve how we measure what matters to humans – like the quality of AI-generated stories.

### Potential Issues In Measuring Latent Constructs
Insights from measurement theory can help us to be cognizant of potential pitfalls when measuring latent constructs. Consider first what is implicitly assumed when we measure something like 'interestingness' by asking “On a scale from 1 to 5, how interesting is this story?”:
* We assume that when humans read stories, something like interestingness exists in their mind as a criterion for judging the story (if it does not exist, what are you measuring?).
* We assume that perceived interestingness is abstract and not directly observable. Unfortunately, there is no little sign lightning up after a person reads a story, saying “For me this story has an interestingness of 3.57”. However, we believe perceived interestigness can be measured by asking the person appropriate questions about it.
* We assume that when a person answers the question “How interesting is this story?”, the perceived interestingness causes at least part of the response.[^1]
     * _We usually assume that there can be other additional causes for the response. But we will typically consider these to be randomly fluctuating measuring error. For example, a person might give a higher rating because she is in a good mood, generally gives high ratings on questionnaires, etc…_

[^1]: This model of measurement is known as the reflective measurement model: Constructs are assumed to cause indicators (responses to questions). The flip side would be a formative measurement model. However, I consider a reflective measurement model to be more appropriate for the assumptions researchers imply when collecting human evaluations, and I will therefore not give further consideration to the formative measurement model.

Problems with this process can arise at different points, but are generally put under two categories:

#### Validity
A _valid_ measure, measures the construct it actually intends to measure. An _invalid_ measure does not provide measurement of the intended construct. Validity has many aspects, and issues with validity can arise for a multitude of reasons.

For example, people might simply not consider 'interestingness' its own independent criterion when judging stories. That is, while it might have appeared plausible in theory, interestingness might turn out to not meaningfully exist as a construct in the real world. Responses to the question “How interesting is this story?” might instead be predicted by a mixture of other factors (for example, the perceived creativity of the story).

Alternatively, 'interestingness' might be a meaningful construct in the real world, but our questions for whatever reason simply fail to capture it and measure something else instead. Say, we tried to measure 'interestingness' by asking, “Was this story nail-biting?”. The question might turn out to measure a combination of tone and pace instead.

Measures with questionable validity are a **serious** threat to the integrity of research results [(Flake & Fried, 2020)](https://journals.sagepub.com/doi/full/10.1177/2515245920952393)! Even worse, whole fields can be led astray, if theoretical frameworks are built upon results from invalid measures. Imagine optimizing models to produce 'interesting' stories, when all measures for 'interestingness' turn out to be invalid (i.e., measuring something else). Models will be optimized for _something_, but for what exactly will be very poorly understood.

#### Reliability

A _reliable_ measure captures whatever it measures with precision. If we use it repeatedly on the same object, we can expect to get a similar result each time with little measurement error. An _unreliable_ instrument lacks precision, and might be basically useless if the issue is severe. That is, reliability describes the degree of measurement error of a measure.

If the scores we are getting from a measure vary wildly, it might not matter whether it does measure what it should measure or not – we simply cannot trust the results we are getting. In other words, we want a measure to be valid _and_ reliable.

<img src="https://upload.wikimedia.org/wikipedia/commons/5/5d/Reliability_and_validity.svg" alt="loss graph" width="400"/></br>

_[© Nevit Dilmen](https://commons.wikimedia.org/wiki/File:Reliability_and_validity.svg)_

### How To Ensure Validity And Reliability
So how do we make sure that our measure for human ratings is valid and reliable? The answer is generally: By using psychometric techniques for validating questionnaires with real-world data.

Ideally, a systematic and rigorous approach is taken starting from the construction of the measure. A good summary of best practices according to insights from psychometric research can for example be found in [Boateng et al. (2018)](https://www.frontiersin.org/articles/10.3389/fpubh.2018.00149/full) and [Hinkin (1998)](https://journals.sagepub.com/doi/abs/10.1177/109442819800100106).

A very brief (and likely overly superficial) overview of the process:
1. _Item Generation_: Define the dimensions to be measured. Note that dimensions are tentative at this point and likely will have to be revised once your theory collides with real-world data. Humans are pesky – they ~~might~~ will react differently to your items than your nice, clean theory suggests.
Then generate items for these dimensions. Base those on existing literature and theory and/or on exploratory research (= talking to people).
2. _Scale Development_: Take your drafted questionnaire and see how people respond to your questions in the real world. The main technique here is analyzing responses to the questions with exploratory factor analysis (EFA) to investigate the underlying factorial structure that explains response patterns on the items. Usually, this step is also used to sort out items that are undesirable for one reason or another.
Ideally, the first version of the questionnaire will be finalized at the end of this step: The researcher will typically have revised the dimensions to be measured and will have selected the ideal set of items to measure those for a first usable version of the scale.
3. _Scale Validation_: Undertake additional studies to validate the scale's validity and reliability. You might want to suggest modifications to the questionnaire based on your results to further refine the measure.

### Existing Measures For Human Evaluations Of Stories: A Second Look
We have now covered enough ground, to discuss the potential issues of existing measures for story quality. In short, I see methodological shortcomings and potentially severe issues with the existing measures.

To my awareness, _none_ of the instruments for human evaluations of AI-generated stories have been evaluated on whether they actually measure anything meaningful (testing validity) or for their precision (testing reliability). As I have just discussed, this represents a _serious_ threat to the usefulness of these measures.

Furthermore, it is very common in the field for each concept (such as 'local contextuality' or 'enjoyability') to be measured with a single item (e.g., [Purdy et al., 2018](https://www.aaai.org/ocs/index.php/AIIDE/AIIDE18/paper/viewFile/18106/17228); [Yao et al., 2019](https://ojs.aaai.org/index.php/AAAI/article/view/4726/4604); [Callan & Foster, 2021](http://ceur-ws.org/Vol-3105/paper9.pdf)). Measuring fairly abstract latent constructs with only one item is known to come at severe psychometric costs ([Furr, 2011](https://methods.sagepub.com/book/scale-construction-and-psychometrics-for-social-and-personality-psychology)): For one, single items are likely to be very imprecise and not capture the full breadth of the construct. Maybe more importantly, many techniques to evaluate the quality of the measure are unavailable or difficult with a single item.[^2] For these reasons, established psychometric guidelines generally recommend 4-6 items per construct for a reliable psychometric evaluation and measurement (e.g., [Hinkins et al., 1998](https://journals.sagepub.com/doi/abs/10.1177/109442819800100106)).

[^2]: Admittedly, this does not matter much in this case, as none of these items have ever been checked for their psychometric quality.

The existing instruments have clearly laid the groundwork for evaluating the quality and nature of AI-generated stories. But as we have seen in the previous section, they currently do so at the risk of producing biased results and misleading theoretical insights. While I do not want to take away from their work, I believe they would benefit from being more thoroughly validated against established psychometrics principles.

## Enter The AI Story Scale
My proposed instrument for evaluating AI-generated stories was developed according to best practices for scale construction: The AI Story Scale (AISS). It is currently the only questionnaire for rating AI-generated stories based on empirical analysis. It should provide a robust instrument to understand how different language models and hyperparameters influence people's experience of the resulting story output. You can find the instrument [here](https://github.com/MWiechmann/ai_story_scale/tree/main/AISS).

I will try to slowly improve and expand this scale with new data.[^3] Links to my studies on the AISS:

[^3]: However, when I say 'slow', I mean _really slow_ – this is still a hobby project of mine!

### [Study 1: Building the AI Story Scale](https://github.com/MWiechmann/ai_story_scale/tree/main/study1_scale_construction)
The initial study for drafting the items for the AISS, and exploring their factorial structure.

It also contains a few proof of concept analyzes to show how the AISS can be used to gain a more detailed understanding of how different generation settings can lead to different type of stories.

# How To Cite The AISS
Go to the [main page of the repo](https://github.com/MWiechmann/ai_story_scale) if you aren't there already, and look to the right to the 'About' field. Click the line that says 'Cite this repository'.
