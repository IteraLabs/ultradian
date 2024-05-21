# Dialogue State Tracking

19:30 - 20:38 

## TL;DR (pragmatic)

While a dialogue is taking place, for each intervention of each participant, words and sentences can be mapped to form the "state" of the dialogue.


## TL;DR (Theoretical)

By usingan ontological dataset, the DST engine can provide elements for improving the understanding of the dialogue context, reduce ambiguity, make more accurate predictions of user intentions. 

- Can be treated as a multi-class classification problem, provided a formal definition of an ontology.
- Google research has a nice frameworked-dataset for this: [The Schema-Guided Dialogue Dataset]("https://github.com/google-research-datasets/dstc8-schema-guided-dialogue")
- Datasets are very context-specific.
- A DST capable model uses all historical data of a dialogue (a sequence of utterances) as input, to predict all (domain, slot) pairs as defined by the ontology, at each dialogue turn.

In the context of Dialogue State Tracking (DST), an ontology refers to a formal representation of concepts, relationships and rules that define the
semantics of a specific domain or task. Also, the ontology serves as a common language and framework for understanding the meaning of entities, relations and, as we 
will see further, actions involved in the dialogue process.

## General structure (informal)

A well-defined ontology for DST:

1. **Entities**: Objects, Individuals or concepts relevant to the conversation.
2. **Relations**: Links between entities.
3. **Actions**: Verbs or actions.
4. **Rules**: Inference rules or constraints that govern how entities interact. 

By using an ontology, a DST system can:

1. **Disambiguate**: Clarify ambiguous terms or phrases by mapping them to specifics within the ontology.
2. **Infer**: Draw conclusions about the dialogue context.
3. **Reason**: Use logical rules to derive new information

```math
S_{i}^{j} = Sim( G_{j} (F(X)), F(u_{i}^{j}) ) \in R^{1} 
```
where:

Sim: Consine similarity
S^{j} \in R^{|u^j|}: Probability Distribution of the $j$-th (domain, slot) pair over its possible values.
G_{j}: Slot projection layer of the $j$ slot
|G|: Number of layers that is equal to the number of (domain, slot) pairs.

## TODO

- Mermaid code for the M2M schema. 

## References

Site about a challenge related to Dialog Systems Technology
> https://sites.google.com/dstc.community/dstc8/home?authuser=0

Data set with schema definition in order to guide training and evaluations for AI Dialogue artifacts
>   https://github.com/google-research-datasets/dstc8-schema-guided-dialogue/tree/master

A "Machines Talking To Machines" (M2) Framework proposed by google.
>   https://arxiv.org/pdf/1801.04871

>   @article{rastogi2019towards,
    title={Towards Scalable Multi-domain Conversational Agents: The Schema-Guided Dialogue Dataset},
    author={Rastogi, Abhinav and Zang, Xiaoxue and Sunkara, Srinivas and Gupta, Raghav and Khaitan, Pranav},
    journal={arXiv preprint arXiv:1909.05855},
    year={2019}}

