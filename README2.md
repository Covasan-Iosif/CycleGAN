# Ablation Study
The study addresses the "I’m Something of a Painter Myself" Kaggle competition, employing a Cycle-Consistent Adversarial Network (CycleGAN) model inspired by the [paper](https://arxiv.org/abs/1703.10593). Unlike the original model, this study utilizes a U-net architecture for both generators, optimizing its ability to learn finer feature relationships with the limited dataset of 300 Monet paintings. The model's streamlined workflow and enhanced training through image augmentation techniques result in superior performance, achieving a MiFID score of 41.45087 on a GPU within a 5-hour training window. This marks a substantial improvement compared
to the baseline model provided by the competition, which attained a score of 53.76998, while training on a more powerful TPU.  <br>

Another approach attempted for the competition involved a cycleGAN utilizing a ResNet architecture with 9 residual blocks for both generators, akin to the implementation in the CycleGAN paper. However, due to limitations related to the small size of the dataset and time constraints, this model does not achieve better results than the one utilizing a U-Net architecture for generators. <br>
However, allowing this model to run for an extended period, approximately 50 epochs, results in superior
values for the adversarial criterion of the generators and discriminators compared to the
model using the U-Net architecture if both models are trained for an equivalent duration.
Therefore, the ResNet model should yield better results on this competition if we alleviate
the time constraints. None of the proposed models in the paper is suitable for running
on CPU, considering the constraints related to the small domain space and time limit of
the competition. <br> <br>
Both U-net and ResNet9 implementations are in this [notebook](https://www.kaggle.com/code/iosifcovasan/photo-to-monet-using-cyclegan)
