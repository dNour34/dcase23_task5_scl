# Supervised Contrastive Learning for Pre-Training Bioacoustic Few-Shot Systems
---

This is the implementation of our work for the challenge DCASE 2023 task 5

Our approach consists in :
<ul>
<li>Training a feature extractor on the training set</li>
<li>Training a linear classifier on each audio of the validation set</li>
</ul>

Firstly, we create the spectrograms of the training set :\
```create_train.py``` : with argument ```--traindir``` for the folder containing the training datasets.

To train the feature extractor :\
```train.py``` : with arguments ```--traindir``` (the same as above), ```--device``` the device to train on, and others concerning training and data augmentation hyperparameters that can be found in ```args.py``` with default values that we used.

To validate the learned feature extractor using 5-shots :\
```evaluate.py``` : with arguments ```--valdir``` for the folder containing the validation datasets, and others concerning hyperparameters that can also be found in ```args.py```. For each submission, use :\
For submission 1 :\
```--ft 0 --ftlr 0.01 --ftepochs 20 --method ce --adam```\
For submission 2 :\
```--ft 1 --ftlr 0.001 --ftepochs 40 --method ce --adam```\
For submission 3 :\
```--ft 2 --ftlr 0.001 --ftepochs 40 --method ce --adam```\
For submission 4 :\
```--ft 3 --ftlr 0.001 --ftepochs 40 --method ce --adam```