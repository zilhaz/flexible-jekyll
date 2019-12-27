---
layout: post
title: CONCEPTUAL ARGUMENTS ON SEMANTIC WEB
date: 2011-12-21 
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: semantic.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [semantic_web] # add tag
---

Lately there has been a lot of discussios going on whether “Semantic Web” is going to be the main feature of Web 3.0 or its just an ambitious vision of Tim Berners-Lee. In this post, I am going to talk about the feasibility of Semantic Web from some conceptual perspectives that mainly includes Syllogism, AI and Godel’s incompletness theorem.

According to Shirky Clay “The Semantic Web is a machine for creating syllogism”. “Syllogism” is one of the most famous contributions of prominent Greek philosopher Aristotle in the study of logic.

A syllogism is a three-step argument with three assertions. The first two steps are called “premises” and the last assertion is called “conclusion”. Here is an example of syllogism –

* 1st assertion (premise): Lancaster University is in Lancaster.
* 2nd assertion (premise): Lancaster is in the UK.
* 3rd assertion (conclusion): Lancaster University is in the UK.

Even though Aristotle discussed about “Syllogism” in 300 BC however the concept of “Ontology” in Semantic Web has a direct relation with Syllogism. This becomes obvious from the example of Ontology Tim Berners-Lee mentioned in his seminal paper on Semantic Web (title: The Semantic Web)  – “If a city code is associated with a state code, and an address uses that city code, then that address has the associated state code”.

Syllogism is an important element of Semantic Web. It helps to discover relations between resources that are true but not explicitly specified.  However, Shirky, Clay argues that, syllogism is not always useful. In real world most of the scenarios are far more complex than above mentioned Tim-Berners-Lee’s example. At times, conclusion in syllogism might be terribly wrong or syllogism might take form of Sorites paradox.

(Sorites paradox: The paradox of the heap of sand is an example of Sorites paradox. If there is N number of grains in a heap of sand and if we start removing grains one-by-one then at some point there will be only one grain left in the heap. As its impossible to decide at which point the left over sand cannot be considered as heap any longer, the last remained grain also should be considered as heap! )

Artificial Intelligence is a frequently discussed topic in Semantic Web literature. Understanding real-world context is an Artificial Intelligence (AI) problem. Even though Semantic Web concept is relatively new, however the researchers have been working on AI for quite a long time. But still AI is far away from being implemented in decision-making activities in real world scenarios. Regarding dealing with real world scenarios, Semantic Web took an opposite direction compare to that of AI. Instead of understanding complex real world scenarios, Semantic Web aims to describe the real world scenarios in less-complex way. However, as we have mentioned earlier, such simplification of real world scenario often shows terrible results. Below is an example of such consequence –

* Statement 1: Mr X lives in England.
* Statement 2: People live in England speaks in English.

Conclusion: Mr X speaks in English.

However, Mr X might be an immigrant who does not speak in English. There is no guaranty that based on N number of factors a system can always decide the real condition of a particular object or scenario.

Global Ontology for Semantic Web also requires agreed standards on the objects/resources. In real world, for number of objects/resources/things there is no universally agreed standards or definition. Furthermore, definitions and standards evolve or change. In small-scale it might be possible (e.g. DBPedia) to agree on common standards for describing objects however for world-wide-web-scale implementation probably this is too ambitious.

In fact, even the campaigners of Semantic Web admits the possibility of paradoxical situations in Semantic Web. According to Tim Berners-Lee, “Semantic Web researchers, in contrast, accept that paradoxes and unanswerable questions are a price that must be paid to achieve versatility”.

Godel’s incompletness theorem  can also go against the concept of Semantic Web. According to W3C’s web document “The Self-describing web” –

“RDF provides an interoperable means of publishing and linking self-describing Web data resources, and for integrating representations rendered using other technologies such as XML. The result is a single, global self-describing Semantic Web that integrates not only resources that are themselves built or represented using RDF, but also the other Web resources to which that RDF links, as well as those that can be mapped to RDF using technologies such as GRDDL” (MENDELSOHN, Noah, 2009)

However, according to Godel’s incompleteness theorem –

“…there would always be some propositions that couldn’t be proven either true or false using the rules and axioms of that mathematical branch itself. You might be able to prove every conceivable statement about numbers within a system by going outside the system in order to come up with new rules and axioms, but by doing so you’ll only create a larger system with its own unprovable statements. The implication is that all logical system of any complexity are, by definition, incomplete; each of them contains, at any given time, more true statements than it can possibly prove according to its own defining set of rules”. (JONES, Judy and WIILSON, William)      

The web has become a part and parcel of our lives. Probably, it is too late to do any new experiment with the fundamental structure of the web. One misinterpretation of semantic meaning might have serious consequence in our lives. The idea of self-describing Linked Data might be appropriate for certain Open Data campaigns but for full blown web-scale implementation a lot more research on the possible consequences should be done. The world may not be ready yet (not even in any near future) to see Pete and Lucy’s (Semantic Web) agents taking all the decisions on behalf of them as mentioned in Tim Berners-Lee’s  seminal paper on Semantic Web.
