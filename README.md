#### HypLiLoc

You can also view at https://github.com/hypliloc/HypLiLoc

💥💥 We have refined the code structure, and this new version can run at **80FPS !** on NVIDIA 3090 GPU.



- Requirements

  PyTorch installation:

  ```
  pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113
  ```

  You can also use the following script:

  ```
  conda install pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch
  ```

  Other dependencies:

  ```
  colour_demosaicing==0.2.2
  geotorch==0.3.0
  matplotlib==3.5.3
  numpy==1.19.5
  open3d==0.15.2
  opencv_python==4.6.0.66
  Pillow==9.3.0
  scipy==1.9.1
  setuptools==63.4.1
  tqdm==4.64.0
  transforms3d==0.4.1
  ```

- Extra dependency pointnet2 installation

  ```
  cd network/pointnet2
  python setup.py install
  cd ..
  cd ..
  ```

- Platform

  ```
  Ubuntu 20.04
  CUDA 11.6
  python 3.8
  ```

- Dataset

  We provide the Oxford Radar dataset that has been pre-processed. 

  https://drive.google.com/file/d/1diGYIxsmFk-CVK0VJXVrBrIVXeRuSHnp/view?usp=share_link

  After downloading, you can unzip it and record the path, e.g. 

  ```
  /home/workstation/Radar_RobotCar/
  ```

  Tips: You can better put the dataset under some folder supported by SSD to achieve fast reading speed.

- Trained weights

  We provide the trained optimal weights for the Full-8 route. 

  https://drive.google.com/file/d/1xunKg82BK2-yOyh7q04AOxL6qL5VKEQE/view?usp=share_link

  After downloading, you can unzip it and put it as

  ```
  HypLiLoc/logs
  ```

- Inference on the Full-8 route

  We have refined the code structure, and the version can run at **80FPS !**

  ```
  python eval.py --data_dir /home/workstation/Radar_RobotCar/ --cuda 0 --scene full8 
  ```

- Train

  ```
  python train.py --data_dir /home/workstation/Radar_RobotCar/ --cuda 0 --scene full8 
  ```

- Other information:

  You can view tools/options.py to set running arguments.