# Protein language models from scratch 

Video lecture series on building generative models of protein sequences. 

Reference implementation: 

- [Protein transformers on GitHub](https://github.com/dacarlin/protein-transformers)


Video lectures: 

| Lecture     |  Description                                                         | Duration | 
|--------------|------------------------------------------------------------------|--------------
| [Lecture 1](https://www.youtube.com/watch?v=c2kFHtuEt8s) |  Choosing a dataset | 15 minutes |
| [Lecture 2](https://youtu.be/8rePVA8rpoY) | A simple protein language model | 30 minutes | 


## Lecture 1. Choosing an appropriate problem for generative modeling of protein sequences  

- [Video for Lecture 1: Choosing a dataset](https://www.youtube.com/watch?v=c2kFHtuEt8s) (15 minutes) 

In this lecture, we'll choose a dataset that we think we can model with a protein transformer model. We'll discuss how I chose this dataset and why I think it makes a good example dataset for this tutorial series. We'll dive into the structure and function of the AcyP enzyme and discuss the various aspects of biological symmetry and enzyme function that make this an interesting problem. We'll look at the structure in PyMOL and look at predicted structures of some of our training data to get an idea of what we are interested in having the model learn. 

Why I chose this particular family to use for this tutorial: 

- enzyme with functional features (such as catalytic residues) 
- short sequence (efficient to train on laptop) 
- large number of examples in UniProt (including annotated active site)
- future datasets of functional scans (from Fordyce Lab)


## Lecture 2. Building a simple language model

- [Video for Lecture 2: Building a simple protein language model](https://youtu.be/8rePVA8rpoY) (30 minutes) 

In this lecture, we'll build a simple language model to model the AcyP proteins in our dataset. We'll discuss representing the protein sequences as integer tokens and build a tokenizer. We'll draw from the foundational NLP literature to build a simple multilayer perceptron (MLP) model that predicts the next amino acid given the previous 3. We'll briefly discuss evaluation of protein language models versus natural language models.  


## Lecture 3. Building a protein language model with a transformer architecture 

In this lecture, we'll expand our language model to a decoder-only transformer architecture, building on the work we have done so far to train a model that's capable of generating new proteins like the AcyP homologs in our training set. We'll build out every aspect of the model from scratch (including the multi-head sequence attention mechanism), train the model, and then we'll show how to generate new sequences from the dataset. [I'd definitely recommend watching Andrej Karpathy's Makemore series](https://www.youtube.com/watch?v=VMj-3S1tku0&list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) which does an amazing job of building up the transformer model step by step conceptually. 


## Lecture 4. Adding in evaluations for protein transformer models  

In this lecture, we'll start talking about evaluating our model. With our new ability to score the likelihood of a sequence under our model, and generate new sequences, we have new questions. How can we tell if our model is any good? We'll do two main things, we'll ste up an automatic ESMFold pipeline, and we'll also put in a numerical eval of the model's ability to predict the effects of mutations using a dataset from Fordyce lab. 


## Lecture 5. Scaling training to 150 M params on UniRef50 using Lambda Labs 

Using all the tricks to achieve efficient model training, we'll scale up our decoder-only transformer model to the size of the smaller ESM and ProGen models (150 M params) and train on the UniRef50 dataset. To do this, we'll use GPU compute from Lambda Labs. 




