# Study 1: Building the AI Story Scale
This is the initial study for drafting the items for the AISS, and exploring their factorial structure. Based on the results of this study, I constructed the version of the AISS.

This study also contains a few proof-of-concept analyzes to show how the AISS can be used to gain a more detailed understanding of how different generation settings can lead to different type of stories.

## Participants
For this study, 398 participants were recruited from two sources: I gathered participants from the community of users of AI storytelling apps as well as from panels for academic research.

* Community: Recruited from community forums of users of AI storytelling apps. Recruitment was carried out on the [NovelAI Discord](https://discord.com/invite/novelai), [NovelAI Reddit](https://discord.com/invite/novelai) and the [AI Multiverse Discord](https://discord.com/invite/puRyrw869h). (165 participants)
* Panels: Recruited from panels for academic research ([SurveySwap.io](https://surveyswap.io/) and [SurveyCircle.com](https://www.surveycircle.com/)). (233 participants)

The survey for participant panels did contain two additional quality-control items to sort out respondents with low data quality. This led to the exclusion of 72 participants. Furthermore, three participants did not provide answers for all items and were also excluded. This left 323 participants for the analysis (162 from the community sample, 161 from the panels sample).

## Item Generation
In order to draft the questions for the AISS, I took stock of existing scales for evaluating different aspects of stories. Existing research that I deemed relevant for evaluating subjective story experiences included are summarized in the following table:

| Authors (Year) | Title | Measured Factors (# Items) | Psychometric Validation? | Notes |
|-|-|-|-|-|
| [Bussele & Bilandzic</br>(2009)](http://hypermedia468.pbworks.com/w/file/fetch/80687372/measuring%20narrative%20engagement.pdf) | Measuring Narrative Engagement | Narrative Engagement (4 Subscales):</br>- Narrative Understanding<br>- Attentional Focus<br>- Narrative Presence<br>- Emptional Engagement</br>(3 per subscale) | Yes<br>(EFA & CFA study) | Scale was originally intended for measuring narrative engagement with movies, and has not been used in research on GLMs.</br>Most measured factors were deemed to high-level for the purpose of judging current stories from GLMs.</br>Only (modified) items for narrative understanding were considered relevant for the AISS. |
| [Purdy, Wang, He, & Riedl</br>(2018)](https://faculty.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | Predicting Generated Story Quality with Quantitative Measures | - Grammaticality</br>- Temporal Ordering</br>- Local Contextuality</br>- Repetition</br>- Interesting Language</br>- Enjoyment</br>- Quality</br>(1 item each) | No | |
| [Tambwekar et al.</br>(2019)](https://arxiv.org/pdf/1809.10736.pdf) | Controllable Neural Story Plot Generation via Reward Shaping  | - Single Plot</br>- Sopa Opera</br>(1 item each) | No | </br>The question on resemblance to a soap opera was specific to the tested model, and not used for this study.</br>Also contained the 7 items from [Purdy et al., 2018](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) |
| [DeLucia, Mueller & Li</br>(2021)](https://arxiv.org/pdf/2010.07375.pdf) | Decoding Methods for Neural Narrative Generation | - Interestingness</br>- Fluency</br>- Coherence</br>- Relevance</br>(1 item each) | No | Original items were [double-barreled](https://en.wikipedia.org/wiki/Double-barreled_question) (or even multiple-barreled) and deemed unnecessarily complex for participants.</br>However, descriptions provided for the factors were quite detailed and were used as inspiration for item generation.</br>Relevance regards the study of the prompt -> output relationship, which is not the current focus of the AISS and was therefore not considered further. |

_Notes: EFA = exploratory factor analysis, CFA = confirmatory factor analysis._

I then categorized these existing items into different hypothesized story aspects. These story aspects were coherence, creativity, general story quality, repetitiveness and writing style.

Furthermore, I interviewed various users of AI storytelling apps to gather feedback on what aspects of AI-generated stories they deem important. Based on these interviews, I reviewed the existing list of items gathered from existing research and decided to add two more tentative story aspects, namely consistent characterization and pace.

After establishing these 7 initial story aspects, I inspected the number of items per story aspect. In accordance with common guidelines for scale construction I aimed for 8-12 provisional items per factor, anticipating that I would discard roughly half of my drafted items ([Hinkins et al., 1998](https://journals.sagepub.com/doi/abs/10.1177/109442819800100106)). Therefore, I drafted additional items as needed in order to create a solid base for later scale construction. This led to a total of 74 provisional items for the first draft of the AISS.

The full list of tentative items, their source, and its final status in regards to the AISS can be viewed when clicking the line below.

<details>
<summary>Click here to view the table with all provisional items.</summary>

| Item | Hypothesized Story Aspect | Source<sup>a | Retained For AISS-v1? | Reason For Elimination | Final Story Aspect |
| ---- | ------------------------- | ------------ | --------------------- | ---------------------- | ------------------ |
I had a hard time making sense of what was going on in the story. | Coherence | [Bussele & Bilandzic (2009)](http://hypermedia468.pbworks.com/w/file/fetch/80687372/measuring%20narrative%20engagement.pdf) | ✖ |  |  |
I had a hard time recognizing the thread of the story. | Coherence|  [Bussele & Bilandzic (2009)](http://hypermedia468.pbworks.com/w/file/fetch/80687372/measuring%20narrative%20engagement.pdf) | ✖ |  |  |
This story’s events occurred in a plausible order. | Coherence | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | ✖ |  |  |
The story appeared to be a single plot. | Coherence | [Tambwekar et al. (2019)](https://arxiv.org/pdf/1809.10736.pdf) | ✔ |  | Coherence |
The plot of the story was plausible. | Coherence | Own | ✔ |  | Coherence |
The story had a clear theme. | Coherence | Own | ✔ |  | Coherence |
The story felt like a coherent story. | Coherence | Own | ✔ |  | Coherence |
The story felt like it contained a bunch of jumbled topics. | Coherence | Own | ✖ |  |  |
The story stayed on topic with a consistent plot. | Coherence | Own | ✖ |  |  |
The story felt like a series of disconnected sentences. | Coherence | Own | ✖ |  |  |
The story had a clearly identifiable plot. | Coherence | Own | ✖ |  |  |
The story lacked logic. | Coherence | Own | ✖ |  |  |
Descriptions of characters in the story were consistent. | Consistent Characterization | Own | ✔ |  | Consistent Characterization |
Characters in the story were described in a contradicting manner. | Consistent Characterization | Own | ✔ |  | Consistent Characterization |
The way the characters were described was inconsistent. | Consistent Characterization | Own | ✔ |  | Consistent Characterization |
The behavior of characters in the story seemed completely random. | Consistent Characterization | Own | ✔ |  | Coherence |
My understanding of the characters in the story is unclear. | Consistent Characterization | Own | ✖ |  |  |
The descriptions of characters in the story were plausible. | Consistent Characterization | Own | ✖ |  |  |
How characters in the story acted seemed implausible. | Consistent Characterization | Own | ✖ |  |  |
It was easy to understand the motivation of the characters in the story. | Consistent Characterization | Own | ✖ |  |  |
This story was enjoyable. | Creativity | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | ✖ |  |  |
The story felt dynamic. | Creativity | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
The story was boring. | Creativity | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
The setting of the story was original. | Creativity | Own | ✔ |  | Creativity/Quality |
The story was innovative. | Creativity | Own | ✔ |  | Creativity/Quality |
The plot development in the story was predictable. | Creativity | Own | ✔ |  | Coherence |
The story was creative. | Creativity | Own | ✖ |  |  |
The story was imaginative. | Creativity | Own | ✖ |  |  |
It was surprising how things turned out in the story. | Creativity | Own | ✖ |  |  |
There were interesting twists and turns in the story. | Creativity | Own | ✖ |  |  |
I was intrigued by the plot. | Creativity | Own | ✖ |  |  |
The story was unconventional. | Creativity | Own | ✖ |  |  |
The plot was typical for this kind of story. | Creativity | Own | ✖ |  |  |
This story was of high quality. | General Quality | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | ✔ |  | Creativity/Quality |
The story was fun to read. | General Quality | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
The story made me want to keep reading. | General Quality | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
The story felt vivid. | General Quality | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
I would like to read more stories like this one. | General Quality | Own | ✔ |  | Creativity/Quality |
I liked this story. | General Quality | Own | ✖ |  |  |
The story was well-written. | General Quality | Own | ✖ |  |  |
The writing style was entertaining. | General Quality | Own | ✖ |  |  |
This story avoided repetition. | Repetitiveness | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | ✖ |  |  |
Many sentences in the story had frequently repeated words and phrases. | Repetitiveness | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
The story was very repetitive. | Repetitiveness | Own | ✖ |  |  |
In the story, the same things happened again and again. | Repetitiveness | Own | ✖ |  |  |
The writing seemed to use the same words over and over. | Repetitiveness | Own | ✖ |  |  |
Characters repeated their actions with little variation. | Repetitiveness | Own | ✖ |  |  |
The plot had no development. | Repetitiveness | Own | ✔ |  | Pace |
One character did something he or she had already done previously in this story. | Repetitiveness | Own | ✖ |  |  |
Characters said or did the same thing many times over. | Repetitiveness | Own | ✖ |  |  |
Characters repeated what other characters had said to them. | Repetitiveness | Own | ✖ |  |  |
Particular words were used too often in the story. | Repetitiveness | Own | ✖ |  |  |
There were similar events that occurred repeatedly in the story. | Repetitiveness | Own | ✖ |  |  |
This story used interesting language. | Writing Style | [Purdy et al. (2018)](https://www.cc.gatech.edu/~riedl/pubs/purdy-aiide18.pdf) | ✖ |  |  |
The story had sentences that were unreadable. | Writing Style | [Inspired by DeLucia, Mueller & Li (2021)](https://arxiv.org/pdf/2010.07375.pdf) | ✖ |  |  |
The story used complex vocabulary. | Writing Style | Own | ✔ |  | Creativity/Quality |
The text contained a broad vocabulary. | Writing Style | Own | ✖ |  |  |
The wording of this text was very precise. | Writing Style | Own | ✖ |  |  |
The text was easy to understand. | Writing Style | Own | ✖ |  |  |
The writing style was too complicated to be understood easily. | Writing Style | Own | ✖ |  |  |
The story contained a great deal of detail. | Writing Style | Own | ✖ |  |  |
The writing style of the story was very good. | Writing Style | Own | ✖ |  |  |
The author's choice of words was elegant. | Writing Style | Own | ✖ |  |  |
The story had no obvious grammatical mistakes. | Writing Style | Own | ✖ |  |  |
The story moved at a fast pace. | Pace | Own | ✔ |  | Pace |
It took a long time for things to happen in the story. | Pace | Own | ✔ |  | Pace |
Nothing seemed to be happening in the story. | Pace | Own | ✔ |  | Pace |
The story was exciting to read. | Pace | Own | ✔ |  | Creativity/Quality |
The story dragged on and on. | Pace | Own | ✖ |  |  |
There was plenty of action in the story. | Pace | Own | ✖ |  |  |
Many things seemed to be happening at once in the story. | Pace | Own | ✖ |  |  |
All elements of the story were relevant to the plot. | Pace | Own | ✖ |  |  |
There's nothing superfluous or unnecessary in this story. | Pace | Own | ✖ |  |  |

_Notes: a = Some items were modified to be more consistent with the rest of the scale._

</details>

## Procedure and Materials
After signing an informed consent, participants first read a story excerpt of roughly 5 minute reading time (_M_ = ??, _SD_ = ??). For participants from the panel sample, the story excerpt was followed by the first quality-control question. Subsequently, participants read...

answered demographic questions, followed by questions on their subjective exposure to ethnic diversity. Subsequently, participants completed the brief version of the Barratt Impulsiveness Scale (BIS-Brief; Steinberg et al., 2013), and the Academic Delay of Gratification Scale (ADOG; Bembenutty & Karabenick, 1998). After completion of the study, participants were thanked for participation and debriefed.