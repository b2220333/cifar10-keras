# cifar10-keras

To train the model, run

python train.py

a training log will be save at the same time.

The structure of CNN:

[CONV 64 + BN + DROP 0.4]
[CONV 64 + BN]
[CONV 64 + BN]
[Pooling 2X2]

[CONV 128 + BN + DROP 0.4]
[CONV 128 + BN]
[CONV 128 + BN]
[Pooling 2X2]

[CONV 256 + BN + DROP 0.4]
[CONV 256 + BN]
[CONV 512 + BN]
[CONV 512 + BN]
[Pooling 2X2]

[Flatten]
[FC 512 + BN + DROP 0.5]
[FC 10]

BN is the batchnormalization that regulize the input of each slice.
It can speed up the training significantly.

Results:
After 300 epochs, this model can reach 91.5% accuracy on the validation 
data with image augmentation.

Each epoch spends 97s on the GTX 1060.

The accuracy should be in the top 20 of Kaggle CIFAR10 competition. 
See the score board https://www.kaggle.com/c/cifar-10/leaderboard
