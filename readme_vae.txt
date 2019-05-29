This folder contains the experiment/code for the language model (vae)
The code is based on https://github.com/jxhe/vae-lagging-encoder

baselines:
    beta-vae: change line 357 to set kl_weight as a constant
    vae: set aggressive is 0
    both baselines need to disable the bn in modules/encoders.enc_lstm (line 59)

folder strucure:
    models: saved models
    modules: src code for the model, due to bn-vae only change the encoder, mainly focus on encoders/
    config: the configuration for different experiments

Requriment:
    python3
    pytorch>=0.4

To prepare data:
    python prepare_data.py

Usave:
    Example script to train VAE on text data (training uses GPU when available):
    
    python text.py --dataset yahoo --aggressive 1 --warm_up 10 --kl_start 0.1
    
    Here:
        --dataset specifies the dataset name, currently it supports synthetic, yahoo, yelp
        --aggressive controls whether applies aggressive training or not
        --kl_start represents starting KL weight (set to 1.0 to disable KL annealing)
        --warm_up represents number of annealing epochs (KL weight increases from kl_start to 1.0 linearly in the first warm_up epochs)
    
    There is no need for testing, because the script weill do testing after training

More details about the code can be found in the original README.md
