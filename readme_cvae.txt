This folder is for the dialogue generation task (bn-cvae)
The code is based on https://github.com/ruotianluo/NeuralDialog-CVAE-pytorch

Requriment:
    python2.7
    pytorch>=0.4

folder structure:
    data: contains the switchboard data
    data_api: dataloader and iterator of the data
    models: the source code of the model
    working: saved checkpoints
        cvae bow: working/run1555563267
        bn-cvae: working/run1559029718
    kgcvae_swda.py: main function
        -word2vec_path pre trained word embedding file location
        -data_dir raw data directory
        -work_dir experiment results directory
        -forward_only only do decoding ( or training (False)
        -test_path the dir to load checkpoint

How to use:
    To train the model:
        python kgcvae_swda.py
    To test the model:
        python kgcvae_swda.py --forward_only True --test_path your_model_path

Generated results:
    cvae: test_cvae.txt
    cvae(bow): test_bow_cvae.txt
    bn-cvae: test_bnvae.txt

