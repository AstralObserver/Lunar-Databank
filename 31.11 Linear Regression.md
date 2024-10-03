For Q number of samples and S features per sample, there are S+1 parameters for the model to adjust for bias.

Linear regression is comprised of a neural network attempting to develop a set of weights that minimize the loss (error margin between guess weights and accuracy).

Common Loss Functions for Regression
- Mean Squared: Average of squared diff between observed and predicted values
- Root Mean Squared: Square root of Mean Squared.
- Mean Absolute: Absolute value of the difference between actual and predicted values.

Mean Squared is heavily influenced by unusual values but Root Mean Squared is not.

Neral networks can preform calculations for Absolute Loss when doing type-classification. To calculate, the observed class has it's % chance of offucing subtracted from it.

Log Loss: The closer the predicted possibilities are to 1 or 0, the closer the log-loss is to 0.
- = -y(ln(p^) + (1-y)ln(1-p^))