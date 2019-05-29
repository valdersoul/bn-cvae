This file contains brief explanation about the dataset and the code.

Requirement:
    python3
    pytorch >= 0.4

Folder strucutre:
    dialogue_nli : data folder
    embeddings: pre trained embeddings
    models: model files

Data: 
    1. Dialogue natural language inference task 
    2. Predict 3 relations between two sentences (entailment, neutral, contradiction)
    3. All data are in jason file, the strucutre will be:
        label: relation between two sentences
        sentence1: the first sentence
            Since my dad is a mechanic we had mostly car books
        sentence2: the second sentence
            My dad is a priest
        Triplet1: triplet of the first sentence
            my_father has_profession machanic
        Triplet2: triplet of the second sentence
            my_father has_projession priest
    4. train/valid/test split is 310110/16500/16500
    5. the original paper: https://arxiv.org/pdf/1811.00671.pdf

code:
    data.py: contains pytorch dataset/dataloader for the task
    utils.py: contains some useful functions for the model
    model.py: the model of ESIM 
    train.py: train script 
    test.py:  test script

    example usage:
        python train.py -f 1024 -e 200
        python test.py -f 1024 -e 200 -m 3