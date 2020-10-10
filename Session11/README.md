# Session 11 - Super Convergence

## Results
 * Network as described is implemented (DevidNET)
 * OneCycleLR sheduler is used:
   - min_lr = 0.001
   - max_lr = 0.02
   - Step up till epochs 5 and and stepdown till the end of epochs 24
   - Epochs = 24
 * Achived expected validation accuracy of **91%**
 * Cylic LR
 * Batch size = 512
 * transform used: Padding-->Randomcrop-->flip-->cutout

