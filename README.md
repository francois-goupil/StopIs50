# StopIs50

`StopIs50` is an end-of-studies project lead by François Goupil and Vincent Romanet at the engineering school of EISTI during their senior year majoring in Artificial Intelligence. 

During this project, we tried to implement a few attacks on the [GTSRB road-signs classifier](http://benchmark.ini.rub.de/?section=gtsrb&subsection=news), amongst the state-of-the-art developped techniques. 

# Model

The model used is VGG16 which we applied pure-transfer learning on. We replaced the FC layers by 3 Dense layers : Dense (256), Dense (512) and Softmax (43) because GTSRB has 43 classes. 
After retraining the FC layers, we obtained a score of roughly 79%. 
The pure-transfered model from VGG16 is the following : [model_pur_transfer_GTSRB_79.h5](https://github.com/francois-goupil/StopIs50/blob/master/Models/VGG16/model_pur_transfer_GTSRB_79.h5) 

# Attacks
You can find the attacks in `Attacks/`
## FGSM
We implemented two FGSM attacks :

### Handmade FGSM
The Jupyter Notebook [FGSM_HandMade_GermanRoadsigns.ipynb](https://github.com/francois-goupil/StopIs50/blob/master/Attacks/FGSM/FGSM_HandMade_GermanRoadsigns.ipynb) implements a handmade version of the attack.

### Cleverhans FGSM
The Jupyter Notebook [FGSM_Cleverhans.ipynb](https://github.com/francois-goupil/StopIs50/blob/master/Attacks/FGSM/FGSM_Cleverhans.ipynb) uses the `Cleverhans` library to implement the attack.


## JSMA
We also tried to implement the JSMA attack but with a lack of time, we could not finish it.
The Jupyter Notebook associated is [JSMA_Cleverhans.ipynb](https://github.com/francois-goupil/StopIs50/blob/master/Attacks/JSMA/JSMA_Cleverhans.ipynb) and uses the `Cleverhans` library as well to implement the attack.


# Libraries
## Cleverhans
`Cleverhans` is the library we mainly used to implement our attacks. You can find it [here](https://github.com/tensorflow/cleverhans).
## Foolbox
`Foolbox` is another library to implement attacks on CNN. You can find it [here](https://github.com/bethgelab/foolbox).
## Adversarial Robustness Toolbox (ART)
`ART` is the last library we found and is developped by IBM. You can find it [here](https://github.com/IBM/adversarial-robustness-toolbox).
