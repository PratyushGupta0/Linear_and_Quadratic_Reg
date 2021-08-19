 Linear_and_Quadratic_Reg
 
 Linear_(a): Linear with loss (a)
 
 Linear_(b): Linear with loss (b)
 
 Quadratic_(c): Quadratic with loss (c)
 
 Quadratic_(d): Quadratic with loss (d)
 
 Dataset: Every sample is a 11-dimensional feature vector, and there are 1200 samples. We initialize random constant weights , whcih we then apply on the randomly generated input
          to get the training ground truth.
 
 In all of the problems, the MSE as a function of epochs has been graphed to geta comparision metric for the different optimizing problems.
 In the end to gauge the accuracy of our algorithm, the 11 dimensional actual weight and optimized weight are plotted against each other, with the actual weights in red and
 calculated weights in blue. 
 
Task 1.1 : MSE loss: 0.42e-05

Task 1.2 : MSE loss: 1.61e-05

Task 1.3 : MSE loss: 0.02

Task 1.4 : MSE loss: 0.15

Loss(a):

This loss is better than the (b) loss as it accounts for the distance between the true and predicted values. When they are very far, it descends quickly and slows the descent
closer to the objective. This results in slightly better results compared to the (b) loss. The problem of exploding and vanishing gradients first appears here. The gradient can
die off close to the objective as there is an exponent of two associated withthe difference. Exploding gradients present a bigger problem. If the loss is too big, then after being
multiplied by the learning rate it has the potential to cause an over-correction. This can lead to the loss in the second iteration being greater than before. This is because of
the cube in the loss. 

Loss (b): 

This loss applies a constant magnitude gradient for any difference between the true and predicted values. This means it does not suffer from the issue of exploding and vanishing
gradients. But this also means that gradient descent can be very slow if the weights are very far from the true weights. Since it does not account for the distance, the initial
values of the trainable weights must be somewhat close to the actual weights. In this case since, bothe the actual and trainabole weights are drawn the same gaussian distribution,
we do not face this issue, However in a general problem, this may be major issue. 

Apart from this there is another problem with this loss. When the weights are very close to their true values, we do not want major changes to the weights. We only want to
gradually nudge the weights in the correct direction. However the constant gradient offered by this loss means there may be an 'overshooting' problem as the gradients over-correct
the weights repeatedly preventing the loss from decresing beyond a certain value. The asymptote seen here is most probably a manifestation of that.


Loss(c)

This loss has even greater problems with vanishing and exploding gradients. Despite that , the weights come out to be reasonably good. 
Since we are squaring the features , it has the potential to cause gradients problems in a similiar way to the losses, since the value of the squared features will be either
significantly smaller or greater than the original input. In 2D terms, we want the loss function to be a roughly circular bowl, however this phenomenon cn cause this bowl to
become elongated and slow down training.

Loss(d)

Due to the very high exponent , the gradients are very unstable and can often explode, hence requiring a low learining rate . Similiarly this loss faces great problems with 
vanishing gradients. This problem was quite severein this case. In the loss graph we can observe a major hump. This is at the start of the second training loop which works at a
learning rate, then there is another smaller hump , further ahead which is due to the third training loop. The deviations in the true and trainable weights are more significant
here than anywhere else despite more training and baby-sitting.
