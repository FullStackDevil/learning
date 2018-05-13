# Sequence 2 Sequence Models

Notes from [Andrew Ng's deeplearning.ai Deep Learning Specialization](https://www.coursera.org/learn/nlp-sequence-models)
[Lecture videos on Coursera](https://www.coursera.org/learn/nlp-sequence-models/lecture/v2pRn/picking-the-most-likely-sentence)

### Basic models

![Sequence to Sequence model](resources/465106B4-C91B-4A94-AB3F-9D6B891BDCB5.png)

use AlexNet as encoder, cut the softmax and then use an encoder for captioning
![Image captioning](resources/A20FBB9E-4417-4D74-AD95-DBF41F859D44.png)

language model: calculates probability of a sentence
can think of Language Model (LM) as a decoder network
with this in mind we can then say that Machine Translation (MT) is a decoder + LM
conditional language model e.g. P(English translation | French sentence)

![MT as conditional LM](resources/6E36FDCD-B718-40F7-866B-7C1026EC7145.png)

![Most likely translation](resources/79024588-EA4F-4630-9592-6B303ECD9D0C.png)

If we've started with
> Jane is ...

Then the next most likley greedy selection might be *going* and a better global sentence will be tossed in greedy search.
![Why not greedy search](resources/AC5AD23F-8615-492E-B010-6903A1B3C389.png)

### Beam Search
Beam width = `B`
Beam width is the number of candidates considered
Let's say `B=3`
![Beam search](resources/BB7C0960-E71F-466F-AEBD-F90869006789.png)

Instantiating 3 copies of the network in each step (i.e. one for each candidate).

![Beam search 3rd step](resources/13819EAC-4C94-49DF-80E6-F39150D7F1F3.png)

If `B=1` then beam search degenerates to greedy search
