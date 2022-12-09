- [Study 1: Building the AI Story Scale](#study-1-building-the-ai-story-scale)
  - [Method](#method)
    - [Participants](#participants)
    - [Item Generation](#item-generation)
    - [Procedure And Materials](#procedure-and-materials)
      - [Story Excerpts](#story-excerpts)
        - [Prompt/Memory Pairs](#promptmemory-pairs)
        - [Generation Settings (Presets)](#generation-settings-presets)
      - [Quality-Control Questions](#quality-control-questions)
  - [Results](#results)
    - [Item Reduction](#item-reduction)
      - [Preliminary Analysis](#preliminary-analysis)
      - [Exploratory Factor Analysis](#exploratory-factor-analysis)

# Study 1: Building the AI Story Scale
This is the initial study for drafting the items for the AISS, and exploring their factorial structure. Based on the results of this study, I constructed the version of the AISS.

This study also contains a few proof-of-concept analyzes to show how the AISS can be used to gain a more detailed understanding of how different generation settings can lead to different types of stories.

## Method
### Participants
For this study, 398 participants were recruited from two sources: I gathered participants from the community of users of AI storytelling apps as well as from panels for academic research.

* Community: Recruited from community forums of users of AI storytelling apps. Recruitment was carried out on the [NovelAI Discord](https://discord.com/invite/novelai), [NovelAI Reddit](https://discord.com/invite/novelai) and the [AI Multiverse Discord](https://discord.com/invite/puRyrw869h). (165 participants)
* Panels: Recruited from panels for academic research ([SurveySwap.io](https://surveyswap.io/) and [SurveyCircle.com](https://www.surveycircle.com/)). (233 participants)

The survey for participant panels did contain two additional quality-control items to sort out respondents with low data quality. This led to excluding 72 participants. Furthermore, three participants did not provide answers for all items and were also excluded. This left 323 participants for the analysis (162 from the community sample, 161 from the panels sample).

### Item Generation
To draft the questions for the AISS, I took stock of existing scales for evaluating different aspects of stories. Existing research that I deemed relevant for evaluating subjective story experiences included are summarized in the following table:

| Authors (Year) | Title | Measured Factors (# Items) | Psychometric Validation? | Notes |
|-|-|-|-|-|
| [Bussele & Bilandzic</br>(2009)](http://hypermedia468.pbworks.com/w/file/fetch/80687372/measuring%20narrative%20engagement.pdf) | Measuring Narrative Engagement | Narrative Engagement (4 Subscales):</br>- Narrative Understanding<br>- Attentional Focus<br>- Narrative Presence<br>- Emptional Engagement</br>(3 per subscale) | Yes<br>(EFA & CFA study) | Scale was originally intended for measuring narrative engagement with movies, and has not been used in research on GLMs.</br>Most measured factors were deemed to high-level for the purpose of judging current stories from GLMs.</br>Only (modified) items for narrative understanding were considered relevant for the AISS. |
| [Purdy, Wang, He, & Riedl</br>(2018)](https://faculty.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | Predicting Generated Story Quality with Quantitative Measures | - Grammaticality</br>- Temporal Ordering</br>- Local Contextuality</br>- Repetition</br>- Interesting Language</br>- Enjoyment</br>- Quality</br>(1 item each) | No | |
| [Tambwekar et al.</br>(2019)](https://arxiv.org/pdf/1809.10736.pdf) | Controllable Neural Story Plot Generation via Reward Shaping  | - Single Plot</br>- Sopa Opera</br>(1 item each) | No | </br>The question on resemblance to a soap opera was specific to the tested model, and not used for this study.</br>Also contained the 7 items from [Purdy et al., 2018](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) |
| [DeLucia, Mueller & Li</br>(2021)](https://arxiv.org/pdf/2010.07375.pdf) | Decoding Methods for Neural Narrative Generation | - Interestingness</br>- Fluency</br>- Coherence</br>- Relevance</br>(1 item each) | No | Original items were [double-barreled](https://en.wikipedia.org/wiki/Double-barreled_question) (or even multiple-barreled) and deemed unnecessarily complex for participants.</br>However, descriptions provided for the factors were quite detailed and were used as inspiration for item generation.</br>Relevance regards the study of the prompt -> output relationship, which is not the current focus of the AISS and was therefore not considered further. |

_Notes: EFA = exploratory factor analysis, CFA = confirmatory factor analysis._

I then categorized these existing items into different hypothesized story aspects. These story aspects were coherence, creativity, general story quality, repetitiveness and writing style.

Furthermore, I interviewed various users of AI storytelling apps to gather feedback on what aspects of AI-generated stories they deem important. Based on these interviews, I reviewed the existing list of items gathered from existing research and decided to add two more tentative story aspects, namely consistent characterization and pace.

After establishing these 7 initial story aspects, I inspected the number of items per story aspect. In accordance with common guidelines for scale construction, I aimed for 8-12 provisional items per factor, anticipating that I would discard roughly half of my drafted items ([Hinkins et al., 1998](https://journals.sagepub.com/doi/abs/10.1177/109442819800100106)). Therefore, I drafted additional items as needed to create a solid base for later scale construction. This led to a total of 73 provisional items for the first draft of the AISS.

All items were to be answered on a 5-point Likert scale, ranging from 1 (strongly disagree) to 5 (strongly agree).

> For the following questions, please think of the story you just read.
> 
> Read each of the following statements and decide how much you agree with each.

The full list of tentative items, their source, and its final status regarding the AISS can be viewed when clicking the line below.

<details>
<summary>Click here to view the table with all provisional items.</summary>

| Item                                                                             | Retained For AISS-v1? | AISS Story Aspect           | Reason For Elimination                                | Hypothesized Story Aspect   | Source<sup>a                                                                                                                  |
| -------------------------------------------------------------------------------- | --------------------- | --------------------------- | ----------------------------------------------------- | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| This story avoided repetition.                                                   | ✔                     | Avoiding Repetition         |                                                       | Repetitiveness              | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf)                                              |
| Many sentences in the story had frequently repeated words and phrases.           | ✔                     | Avoiding Repetition         |                                                       | Repetitiveness              | Inspired by [DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| Characters repeated what other characters had said to them.                      | ✔                     | Avoiding Repetition         |                                                       | Repetitiveness              | Own                                                                                                                           |
| One character did something he or she had already done previously in this story. | ✔                     | Avoiding Repetition         |                                                       | Repetitiveness              | Own                                                                                                                           |
| Characters said or did the same thing many times over.                           | ✔                     | Avoiding Repetition         |                                                       | Repetitiveness              | Own                                                                                                                           |
| Characters repeated their actions with little variation.                         | ✔                     | Avoiding Repetition         |                                                       | Repetitiveness              | Own                                                                                                                           |
| I had a hard time recognizing the thread of the story.                           | ✔                     | Coherence                   |                                                       | Coherence                   | [Bussele & Bilandzic (2009)](http://hypermedia468.pbworks.com/w/file/fetch/80687372/measuring%20narrative%20engagement.pdf) |
| This story’s events occurred in a plausible order.                               | ✔                     | Coherence                   |                                                       | Coherence                   | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf)                                              |
| The story appeared to be a single plot.                                          | ✔                     | Coherence                   |                                                       | Coherence                   | [Tambwekar et al. (2019)](https://arxiv.org/pdf/1809.10736.pdf)                                                             |
| The story had a clear theme.                                                     | ✔                     | Coherence                   |                                                       | Coherence                   | Own                                                                                                                           |
| The plot of the story was plausible.                                             | ✔                     | Coherence                   |                                                       | Coherence                   | Own                                                                                                                           |
| The story felt like a coherent story.                                            | ✔                     | Coherence                   |                                                       | Coherence                   | Own                                                                                                                           |
| All elements of the story were relevant to the plot.                             | ✔                     | Coherence                   |                                                       | Pace                        | Own                                                                                                                           |
| Characters in the story were described in a contradicting manner.                | ✔                     | Consistent Characterization | Consistent Characterization                           | Own                         |
| The way the characters were described was inconsistent.                          | ✔                     | Consistent Characterization | Consistent Characterization                           | Own                         |
| The story was innovative.                                                        | ✔                     | Creativity/Quality          |                                                       | Creativity                  | Own                                                                                                                           |
| The setting of the story was original.                                           | ✔                     | Creativity/Quality          |                                                       | Creativity                  | Own                                                                                                                           |
| This story was of high quality.                                                  | ✔                     | Creativity/Quality          |                                                       | General Quality             | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf)                                              |
| I would like to read more stories like this one.                                 | ✔                     | Creativity/Quality          |                                                       | General Quality             | Own                                                                                                                           |
| The story moved at a fast pace.                                                  | ✔                     | Pace                        |                                                       | Pace                        | Own                                                                                                                           |
| It took a long time for things to happen in the story.                           | ✔                     | Pace                        |                                                       | Pace                        | Own                                                                                                                           |
| Nothing seemed to be happening in the story.                                     | ✔                     | Pace                        |                                                       | Pace                        | Own                                                                                                                           |
| The plot had no development.                                                     | ✔                     | Pace                        |                                                       | Repetitiveness              | Own                                                                                                                           |
| I had a hard time making sense of what was going on in the story.                | ✖                     |                             | Multicollinearity / Redundancy                        | Coherence                   | [Bussele & Bilandzic (2009)](http://hypermedia468.pbworks.com/w/file/fetch/80687372/measuring%20narrative%20engagement.pdf) |
| The story felt like a series of disconnected sentences.                          | ✖                     |                             | High cross-loadings                                   | Coherence                   | Own                                                                                                                           |
| The story stayed on topic with a consistent plot.                                | ✖                     |                             | Multicollinearity / Redundancy                        | Coherence                   | Own                                                                                                                           |
| The story felt like it contained a bunch of jumbled topics.                      | ✖                     |                             | Multicollinearity / Redundancy                        | Coherence                   | Own                                                                                                                           |
| The story had a clearly identifiable plot.                                       | ✖                     |                             | Multicollinearity / Redundancy                        | Coherence                   | Own                                                                                                                           |
| The story lacked logic.                                                          | ✖                     |                             | Multicollinearity / Redundancy                        | Coherence                   | Own                                                                                                                           |
| It was easy to understand the motivation of the characters in the story.         | ✖                     |                             | High cross-loadings                                   | Consistent Characterization | Own                                                                                                                           |
| How characters in the story acted seemed implausible.                            | ✖                     |                             | Low main loading                                      | Consistent Characterization | Own                                                                                                                           |
| Descriptions of characters in the story were consistent.                         | ✖                     |                             | Multicollinearity / Redundancy                        | Consistent Characterization | Own                                                                                                                           |
| The behavior of characters in the story seemed completely random.                | ✖                     |                             | Multicollinearity / Redundancy                        | Consistent Characterization | Own                                                                                                                           |
| My understanding of the characters in the story is unclear.                      | ✖                     |                             | Multicollinearity / Redundancy                        | Consistent Characterization | Own                                                                                                                           |
| The descriptions of characters in the story were plausible.                      | ✖                     |                             | Multicollinearity / Redundancy                        | Consistent Characterization | Own                                                                                                                           |
| The story was boring.                                                            | ✖                     |                             | Multicollinearity / Redundancy                        | Creativity                  | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| The story felt dynamic.                                                          | ✖                     |                             | High cross-loadings                                   | Creativity                  | Inspired by [DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| The plot development in the story was predictable.                               | ✖                     |                             | Detrimental to Omega Hierachical (Coherence)          | Creativity                  | Own                                                                                                                           |
| There were interesting twists and turns in the story.                            | ✖                     |                             | High cross-loadings                                   | Creativity                  | Own                                                                                                                           |
| It was surprising how things turned out in the story.                            | ✖                     |                             | Low main loading                                      | Creativity                  | Own                                                                                                                           |
| The story was creative.                                                          | ✖                     |                             | Multicollinearity / Redundancy                        | Creativity                  | Own                                                                                                                           |
| The story was imaginative.                                                       | ✖                     |                             | Multicollinearity / Redundancy                        | Creativity                  | Own                                                                                                                           |
| I was intrigued by the plot.                                                     | ✖                     |                             | Multicollinearity / Redundancy                        | Creativity                  | Own                                                                                                                           |
| The story was unconventional.                                                    | ✖                     |                             | Multicollinearity / Redundancy                        | Creativity                  | Own                                                                                                                           |
| The plot was typical for this kind of story.                                     | ✖                     |                             | Multicollinearity / Redundancy                        | Creativity                  | Own                                                                                                                           |
| The story was fun to read.                                                       | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | Inspired by [DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| The story made me want to keep reading.                                          | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | Inspired by [DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| The story felt vivid.                                                            | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | Inspired by [DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| This story was enjoyable.                                                        | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf)                                              |
| I liked this story.                                                              | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | Own                                                                                                                           |
| The story was well-written.                                                      | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | Own                                                                                                                           |
| The writing style was entertaining.                                              | ✖                     |                             | Multicollinearity / Redundancy                        | General Quality             | Own                                                                                                                           |
| Many things seemed to be happening at once in the story.                         | ✖                     |                             | Detrimental to Omega Hierachical (Coherence)          | Pace                        | Own                                                                                                                           |
| There was plenty of action in the story.                                         | ✖                     |                             | High cross-loadings                                   | Pace                        | Own                                                                                                                           |
| The story dragged on and on.                                                     | ✖                     |                             | High cross-loadings                                   | Pace                        | Own                                                                                                                           |
| There’s nothing superfluous or unnecessary in this story.                        | ✖                     |                             | Low main loading                                      | Pace                        | Own                                                                                                                           |
| The story was exciting to read.                                                  | ✖                     |                             | Multicollinearity / Redundancy                        | Pace                        | Own                                                                                                                           |
| The story was very repetitive.                                                   | ✖                     |                             | Multicollinearity / Redundancy                        | Repetitiveness              | Own                                                                                                                           |
| In the story, the same things happened again and again.                          | ✖                     |                             | Multicollinearity / Redundancy                        | Repetitiveness              | Own                                                                                                                           |
| The writing seemed to use the same words over and over.                          | ✖                     |                             | Multicollinearity / Redundancy                        | Repetitiveness              | Own                                                                                                                           |
| Particular words were used too often in the story.                               | ✖                     |                             | Multicollinearity / Redundancy                        | Repetitiveness              | Own                                                                                                                           |
| There were similar events that occurred repeatedly in the story.                 | ✖                     |                             | Multicollinearity / Redundancy                        | Repetitiveness              | Own                                                                                                                           |
| This story used interesting language.                                            | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf)                                              |
| The story had sentences that were unreadable.                                    | ✖                     |                             | Low main loading                                      | Writing Style               | Inspired by [DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf)                                            |
| The story used complex vocabulary.                                               | ✖                     |                             | Detrimental to Omega Hierachical (Creativity/Quality) | Writing Style               | Own                                                                                                                           |
| The story contained a great deal of detail.                                      | ✖                     |                             | Detrimental to Omega Hierachical (Creativity/Quality) | Writing Style               | Own                                                                                                                           |
| The text was easy to understand.                                                 | ✖                     |                             | Low Communality                                       | Writing Style               | Own                                                                                                                           |
| The writing style was too complicated to be understood easily.                   | ✖                     |                             | Low main loading                                      | Writing Style               | Own                                                                                                                           |
| The text contained a broad vocabulary.                                           | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | Own                                                                                                                           |
| The wording of this text was very precise.                                       | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | Own                                                                                                                           |
| The story contained a great deal of detail.                                      | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | Own                                                                                                                           |
| The writing style of the story was very good.                                    | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | Own                                                                                                                           |
| The author’s choice of words was elegant.                                        | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | Own                                                                                                                           |
| The story had no obvious grammatical mistakes.                                   | ✖                     |                             | Multicollinearity / Redundancy                        | Writing Style               | Own                                                                                                                           |

_Notes: a = Some items were modified to be more consistent with the rest of the scale._

</details>

### Procedure And Materials
After signing an informed consent, participants first read a story excerpt generated by a generative pre-trained transformer (GPT) model. Each story excerpt had a reading time of roughly 5 minutes. For participants from the panel sample, the story excerpt was followed by the first quality-control question. Subsequently, participants evaluated the story excerpts on the 73 provisional items for the AISS. For the panel sample, a further quality-control question was mixed in the provisional AISS items.
#### Story Excerpts
320 Story excerpts were generated by using the [NovelAI Research Tool (`nrt`)](https://github.com/wbrown/novelai-research-tool). Through `nrt`, a short prompt and "memory" text (explained below) was sent to Euterpe, a finetune of the [Fairseq GPT-13B model](https://github.com/facebookresearch/fairseq/tree/main/examples/moe_lm) offered by [NovelAI](https://novelai.net/). The prompt and memory text served to establish the genre (High Fantasy, Hard Sci-Fi, Historical Romance or Horror). For each story excerpt, Euterpe ran through 30 generations using one NAI's predefined generation settings (called "presets" within NAI). A total of 8 default presets was used for story generation, and the max character length set to 40. The results were 320 story excerpts (40 per preset) with a word count of 744 to 1499 (_M_ = 1175.17, _SD_ = 117.12, about 5 minutes reading time).

##### Prompt/Memory Pairs
Story generation made use of a prompt and "memory" text. The prompt formed the base for the initial input to the model. In addition, the "memory" functionality of NAI was used. Memory in this context denotes a set of tokens that is always used to build the top of the context window. This is a way to ensure that the model always "remembers" a certain set of tokens essentially to the story generation. In this case, the memory function was used to ensure that the model always remembered the genre of the story. Stories in the NAI finetune corpus are known to be manually meta-tagged in the following manner

```
[Author: <Author Name>; Title: <Title>; Tags: <Tags>; Genre: <Genre>]
```

As an example, a hypothetical book from J.K. Rowling could be tagged as:

```
[ Author: J.K. Rowling; Title: The Raining Night; Tags: deserted tropical island, time travel; Genre: horror ]
```

As I was only interested in keeping the genre at least somewhat consistent for one specific memory/prompt pair, only the `Genre:` tag was used. The specific memory/prompt pairs used for the study are listed below:

| Label | Memory | Prompt |
|---|---|---|
| **Hard Sci-Fi** | \[ Author: ; Tags: ; Genre: Hard Sci-fi \] | "I have a message for you from the president," said Dr. Sato, handing over an envelope to me. "He's asking that we meet with him at his office this afternoon." I took it and thanked her before walking out of my apartment building into the bright sun. It was already noon on Mars—the longest day in the year here on the planet. |
| **High Fantasy** | \[ Author: ; Tags: ; Genre: High Fantasy \] | The sun was high in the sky when they arrived at their destination. The valley of the River Tethys flowed into a wide, shallow lake surrounded by mountains on all sides. A small village sat along its shores with two towers standing guard over it from either side like sentinels. It looked to be deserted but for some smoke rising up out of chimneys and the occasional bird flying overhead or flitting through trees. |
| **Historical Romance** | \[ Author: ; Tags: ; Genre: Historical Romance \] | The first time he saw her, the sight of her was like a slap across his face. She'd come into the tavern where he worked and sat at one of the tables in front of him. |
| **Horror** | \[ Author: ; Tags: ; Genre: Horror \] | I woke up to hear knocking on glass. At first, I thought it was the window until I heard it come from the mirror again. I got out of bed and walked over to the mirror. When I looked into it, there was a face looking back at me. |

##### Generation Settings (Presets)
NAI presets are a predefined batch of settings for the text generation. The reason for choosing the different generation settings offered by NAI was to ensure using sets of settings that had already been tested and found to be useful for story generation for a commercial product. The presets used for this study are listed below (using their names given by NAI):

| label | temperature | max_length | min_length | top_k | top_p | top_a | tail_free_sampling | repetition_penalty | repetition_penalty_range | repetition_penalty_slope | repetition_penalty_frequency | repetition_penalty_presence | order |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ace of Spades (14/02/2022) | 1.15 | 40 | 1 | 0 | 0.95 | 1 | 0.8 | 2.75 | 2048 | 7.02 | 0 | 0 | TFS, Top-p, Top-k, Temperature |
| All-Nighter (14/02/2022) | 1.33 | 40 | 1 | 13 | 1 | 1 | 0.836 | 2.366 | 400 | 0.33 | 0.01 | 0 | TFS, Top-p, Top-k, Temperature |
| Basic Coherence (14/02/2022) | 0.585 | 40 | 1 | 0 | 1 | 1 | 0.87 | 3.05 | 2048 | 0.33 | 0 | 0 | Temperature, Top-k, Top-p, TFS |
| Fandango (14/02/2022) | 0.86 | 40 | 1 | 20 | 0.95 | 1 | 1 | 2.25 | 2048 | 0.09 | 0 | 0 | Top-p, Top-k, TFS, Temperature |
| Genesis (14/02/2022) |  0.63 | 40 | 1 | 0 | 0.975 | 1 | 0.975 | 2.975 | 2048 | 0.09 | 0 | 0 | Top-p, Top-k, TFS, Temperature |
| Low Rider (14/02/2022) |  0.94 | 40 | 1 | 12 | 1 | 1 | 0.94 | 2.66 | 2048 | 0.18 | 0.013 | 0 | Top-p, Top-k, TFS, Temperature |
| Morpho (14/02/2022) | 0.6889 | 40 | 1 | 0 | 1 | 1 | 1 | 1 | 2048 | 0 | 0.1 | 0 | Temperature, Top-k, Top-p, TFS |
| Ouroboros (14/02/2022) | 1.07 | 40 | 1 | 264 | 1 | 1 | 0.925 | 2.165 | 404 | 0.84 | 0 | 0 | Top-k, Temperature, TFS, Top-p |

Documentation for the NAI API, including valid value ranges for the generation settings, can be found [here](https://api.novelai.net/docs/).

#### Quality-Control Questions
To ensure that participants from the panel sample were providing valid responses, two quality-control questions were included in the survey.

The first question immediatly followed the story excerpt and asked the participant how the story they just read began. The participant was asked to select one of six options. If the chosen option coincided with the content of the story, the first quality check was passed.

> The story I just read, began with...
> *   ...with a message from the president.
> *   ...the description of a small village.
> *   ...a noise coming from a mirror.
> *   ...someone working in a tavern.
> *   ...two armies clashing in a battle.
> *   ...someone waking up in a spaceship.

The second question was mixed in with the provisional AISS items and simply stated:

> This is a quality check. Please select "Somewhat disagree".

To pass this quality check, the participant had to select "Somewhat disagree" for this item.

## Results
### Item Reduction
#### Preliminary Analysis
Initial inspection of the intercorrelations between the items showed a sufficient number of correlations above the recommended threshold of |_r_| > .3 ([Tabachnik, Fidell, 2018](https://www.pearson.com/en-us/subject-catalog/p/using-multivariate-statistics/P200000003097?view=educator)). However, the determinant was far below the recommend threshold of _det_ > .00001, indicating strong multicollinearity and the presence of redundant items. To address this issue, I removed the item with the highest variance inflation factor (VIF) in an iterative process, until the determinant was above .00001. This resulted in the exclusion of 42 questions with 31 remaining items, _det_ = 00002.
The appropriateness of exploratory factor analysis (EFA) for this data was assessed using the Kaiser-Meyer-Olkin (KMO) measure of sampling adequacy. The KMO indicated that the data was well-suited for EFA, _KMO_ = .86.
#### Exploratory Factor Analysis
The EFA was conducted using the minimum residual (MINRES) algorithm.
##### Number Of Factors
The decision on the number of factors to retain was based on a [parallel analysis](

... use 10% standard of 99th percentile!