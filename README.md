# autoencoder
Autoencoder vs Variational Autoencoder for anomaly detection.<br>
The dataset is an treated as unlabelled financial transactions<br>
but data does provide which transactions are anomalies.<br>
7% of data were anomalies. <br>
<br>
**Results**
Autoencoder
![image](https://user-images.githubusercontent.com/45408401/218049193-b3d92184-236f-4dc6-8049-12d9dbbf6dae.png)
<br>
VAE
![image](https://user-images.githubusercontent.com/45408401/218048987-e8d72ad6-a806-4970-9b07-dcefc1692a12.png)

**Reflection**
<br>
The accuracy was misleading for the AE and VAE.
When using the classification report, the performance of the models was
revealed.
The finalized models both have the same architecture. With approximately 2900
params. This provided robust models, which is needed with a random data
set. Sometimes the precision, recall and f1 score can reach as low as .79
and up to .96 depending on the data split.

When the layers were increased to approx. 5000 the model didn't perform better
and in some cases worse. It was noted that the VAE was more sensitive to
the increase and performed poorly while the AE performed similar to the
optimal model.

Less layers did perform just as well as the current model, but when the data
split unfavourably the lessening layers saw a drop to as low as .06 on the anonalies for precision, recall, and f1 score.

Therefore around the 3,000 params mark with precautions taken for overfitting
and local minimas in terms of kernel optimizers and dropout layers seemed
to give the best overall model.

Comparison
The AE generally outperformed the VAE which is uncommon as VAE's use the
reparmeterization to improve generalization. This happened when the layers
were adjusted (increased and decreased) and unfavourable data splits
occured. Reasoning from this outcome and the model architecture, the small
latent space might be the cause of this, with a dimension of 2. Another
possibilty is that the VAE is suffering from a irregular latent space while
AE is better able to combat this, but this is less likely given the data has only 9 inputs.

