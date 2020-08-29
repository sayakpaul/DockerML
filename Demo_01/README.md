This demo trains a very simple [`RandomForestRegressor`](http://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html) model on the [Wine Quality dataset](https://www.kaggle.com/uciml/red-wine-quality-cortez-et-al-2009) and logs the results to a [Weights and Biases](https://www.wandb.com/) (`wandb`) dashboard. After running `docker run` you should get a `wandb` run page link (like this - https://app.wandb.ai/sayakpaul/docker-wandb/runs/rnm18wsz) in the output. 

The code in the `train.py` script has been adapted from [here](https://github.com/elleobrien/wine/). 

## Steps
1. Open up a terminal and set up the environment variable `WANDB_KEY`. An example - 
`export WANDB_KEY=...`. This should point to the API key of your `wandb` account. You can generate the API key from here: https://app.wandb.ai/authorize. 
2. Execute the following - 
   
   ```
   $ docker build -t <IMAGE_NAME>:<TAG> .
   $ docker run -e WANDB_KEY=$WANDB_KEY <IMAGE_NAME>:<TAG>
   ```

   An example - 
   ```
   $ docker build -t wandb:v1 .
   $ docker run -e WANDB_KEY=$WANDB_KEY wandb:v1
   ```