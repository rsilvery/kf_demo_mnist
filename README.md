## Demo of KubeFlow
This demo is to train and serve a TensorFlow MNIST model. Training is done in the notebook container on data in the MapR volume and model is output back to MapR storage.

### Train Model
* Launch Jupyter instance with TensorFlow from JupyterHub (located on port 8000)
* Open [mnist.ipynb](mnist.ipynb) notebook 
* Set your training_data and model_output directories to the correct location in the MapR filesystem.
  * Note that the mount point is under */home/jovyan* so if your directory was mounted as *training_data* it will be */home/jovyan/training_data*
* Run training job 

### Serve Model
* Copy [model.py](model.py) executable code to the same directory as your model: (ex. /user/mapr/kubeflow/models/mnist)
* Run Kubectl with [serve_mnist.yaml](serve_mnist.yaml)
  ```
  kubectl create -f serve_mnist.yaml
  ```
  This uses the mount point from the kf-pvc Persistent Volume which must point to the directory in MapR-FS which contains the model and model executable code (model.py).

### Test Model
* 





...to be continued.



