# Cross-Video Exploration for WSTAL

### Recommended Env
- Python 3.8
- Pytorch 1.8.1
- CUDA 12.1


### Data Preparation
1.  [THUMOS'14](https://www.crcv.ucf.edu/THUMOS14/)
    - use the features and annotations provided by [this repo](https://github.com/sujoyp/wtalc-pytorch).

2. Place the [features](https://emailucr-my.sharepoint.com/personal/sujoy_paul_email_ucr_edu/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Fsujoy%5Fpaul%5Femail%5Fucr%5Fedu%2FDocuments%2Fwtalc%2Dfeatures&ga=1) and [annotations](https://github.com/sujoyp/wtalc-pytorch/tree/master/Thumos14reduced-Annotations) inside a `dataset/Thumos14reduced/` folder.



### Training
You can easily train the model by running the provided script.

- Refer to `options.py`. Modify the argument of `dataset-root` to the path of your `dataset` folder.

- Run the command below.

~~~~
$ python main.py --run-type 0 --model-id 1
~~~~

Models are saved in `./ckpt/dataset_name/model_id/`

### Evaulation

#### 
The trained model can be found [here](https://drive.google.com/file/d/1xgyebFW75B08hJrXarmK5ZQ6F5iahg4A/view?usp=sharing). (This saved model's result is slightly different from the one reported in our paper.)

Please put it into `./ckpt/dataset_name/model_id/`.

- Run the command below.

~~~~
$ python main.py --pretrained --run-type 1 --model-id 1
~~~~

Please refer to the log in the same folder of saved models to set the load epoch of the best model.
Make sure you set the right `model-id` that corresponds to the `model-id` during training.


