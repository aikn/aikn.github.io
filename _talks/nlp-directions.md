---
title: 'Some NLP results'
collection: talks
date: 2024-01-25
teaser: and MT/TTS directions
permalink: /log/nlp-directions
author_profile: false
tags:
  - MT
  - TTS
  - NLP
---


Machine translation (MT) and text-to-speech (TTS) were the two problems that I have closely worked on and in both cases on very related themes focussing on improved interactivity and controllable modelling, and better sample efficiency in training.
In MT, this involved interactive and automatic post-editing of model outputs for better quality while controlling various other attributes.
Attributes like verbosity or readability of the generated translation, handling ambiguity in context like gender, handling resource imbalance when working together with both low-resource and high-resource languages.
Similarly in TTS the focus was on improving emotiveness of generated speech, to make outputs sound closer to that of humans for conversational HCI systems and improving data efficiency for scaling to new languages.


Our experience (see [1]) is that as the base models become bigger and stronger, which is increasingly the case in practice now along LLMs, there are diminishing returns to gain from automatic post-editing. 
The other alternative was to try interactive editing with humans in the loop by surfacing only those outputs that need attention and surfacing alternatives with simple feedback.
While these are good models that add value to such high value content (see [2]), it is a very challenging HCI problem to design is suitably for specific operational use-cases.
Similar is our learning from TTS models (see [3]) where we improve the emotiveness of generated speech outputs and the control can be handled through human inputs on prosodic preferences, but again, there is huge gaps to fill on the modelling-side as much as there is on HCI for them to be good for adoption.
Further, all models amplify various issues arising out of resource disparity that pronouncing linguistic errors like, for example, the word "you" in EN is neutral on gender, neutrality and plurality that needs more context when working with languages that needs that context.
Cleaned data for resource rich languages like Common Crawl can have as much as about ten times the data for the bottom forty put together.
The disparity is even worse in speech data because speech data is harder to collect than text especially clean speech with transcripts that requires studio expensive recording environment and transcribers but also because dialects make the space larger than that of text.
This necessitates bringing down the minimum data required to extend models to new languages.
Our work in [4] proposes a TTS architecture that reuses self-supervised learning (SSL) models to reduce the data dependence by more than a factor of six so that TTS can be extended to a new language with as little as five hours of transcribed speech. 
It even supports de novo languages if the base SSL covers the acoustics well for it.


References
----

1. _Adapting neural machine translation for automatic post-editing_ with Abhishek Sharma, Prabhakar Gupta, in Conference on Machine Translation (WMT) 2021. [On ACL](https://aclanthology.org/2021.wmt-1.35/).
2. _Interactive post-editing for verbosity controlled translation_ with Prabhakar Gupta, Anil Nelakanti, Grant M. Berry, Abhishek Sharma, in COLING Conference, 2022. [On ACL](https://aclanthology.org/2022.coling-1.454/).
3. _Empathic machines: using intermediate features as levers to emulate emotions in text-to-speech system_ with Saiteja Kosgi, Sarath Sivaprasad, Niranjan Pedanekar, Vineet Gandhi in NAACL Conference 2022 [On ACL](https://aclanthology.org/2022.naacl-main.26/).
4. _ParrotTTS: Text-to-speech synthesis exploiting disentangled self-supervised representations_ with Neil Shah, Saiteja Kosgi, Vishal Tambrahallia, Neha Sahipjohn, Niranjan Pedanekar, and Vineet Gandhi in EACL Conference 2024. [On Arxiv](https://arxiv.org/abs/2303.01261v2).
