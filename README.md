<div>
  <h1 align="center">
    Model Development for Push-Up Counting By Utilizing Body Landmarks and LSTM Algorithm
  </h1>
  <div align="center">
    <img src="https://github.com/ItMeBayu/ItMeBayu/blob/main/assets/push-up_classification/cover.png" alt="Push-up Counting By Utilizing Body Landmarks and LSTM Algorithm" width="400">
  </div>
  
  <br>
  <h2> Description</h2>
  <p>
    Building a model to classify and evaluate push-up movements by processing initial data in the form of videos using MediaPipe Pose to obtain body landmark data that is processed until it is ready to become a dataset for training. The result is the best model with an accuracy of 90.02% in testing. In addition to building the model, a simple simulation was also built using Python that runs in real time, and the test results with the simulation obtained an accuracy of 95.05%. Thus, the model can properly recognize and classify push-up movements.
  </p>
  <a href="https://ojs.stmik-banjarbaru.ac.id/index.php/jutisi/article/view/3363">Publication 1</a>
  <a href="">Publication 2</a>
</div>
<br>
<div>
  <h2> Results </h2>
    <p>Training and testing process graph of the best model</p>
    <details>
      <summary>Accuraccy & Loss</summary>
      <img src="https://github.com/ItMeBayu/ItMeBayu/blob/main/assets/push-up_classification/log_training.png" alt="Accuracy & Loss Model" class="dropdown-image" width="800">
    </details>
    <details>
      <summary>Confusion Matrix</summary>
      <img src="https://github.com/ItMeBayu/ItMeBayu/blob/main/assets/push-up_classification/confusion_matrix.png" alt="Confusion Matrix" class="dropdown-image" width="500">
    </details>
    <details>
      <summary>Video Testing Simulation</summary>
      <p align="center">
        <a href="https://youtu.be/BM2rLyKfvcE">
          <img src="https://github.com/ItMeBayu/ItMeBayu/blob/main/assets/push-up_classification/youtube12.png" width=300">
        </a>
      </p>
    </details>
</div>
<br>
<div>
  <h2>Research Process</h2>
    <h4>Stage 1: Data Collection</h4>
      <p>Collecting video data taken from six angles, namely left parallel, upper left, lower left, front left parallel, front left upper, and front left lower. This data was validated by a validator who is a physical trainer at Secata Rindam IX/Udayana Singaraja. </p>
    <h4>Stage 2: Video Data Processing</h4>
      <p>The video data collection results show 5 repetitions in each video. At this stage, the video data is cut into 1 video containing only 1 repetition using the CapCut Desktop application. At this stage, augmentation is also carried out where all videos are flipped to obtain data from the right side of the body. So, from this stage, the camera angle used is 12 degrees in accordance with the data collection angle and from the right side. The result of this process yields a total of 3,600 video data points evenly distributed across 10 classes. The 10 classes are correct, incorrect-down-half, incorrect-hip-up, incorrect-up-half, incorrect-hip-up-down-half, incorrect-hip-up-up-half, incorrect-knee-bend, incorrect-knee-bend-down-half, incorrect-knee-bend-up-half, and incorrect-only-body-up.</p>
    <h4>Stage 3: Landmark and Feature Extraction</h4>
      <p>Once the video data is ready for use, the extraction process is carried out using MediaPipe Pose, then 7 keypoints are selected and 4 joint angles are calculated based on the side of the body facing the camera. Due to differences in data length, a padding process is carried out to make the data the same length and ready for use in model training.</p>
    <h4>Model Training and Testing</h4>
      <p>Before training the model, the data will first be divided into training and testing data with a ratio of 80:20. Later, K-Fold Cross Validation will be used in the training and also use early stopping to get the best model. The training stages are also divided into two stages.</p>
      <div>
        <div>
          <h5>    First Stage Training</h6>
          <p>  In the first stage, training was conducted by testing eight different architectures to find the optimal layer combination. Using the Adam optimizer.</p>
        </div>
          <div>
            <h5>  Second Stage Training</h6>
            <p> In the second stage of the training process, hyperparameter optimization was carried out in the form of learning rate values and the addition of regularization. The architecture used was the best from the first stage. In this stage, a total of 11 training sessions were carried out with different configurations.</p>
          </div>
      </div>
    <h4>Simulation Development and Testing</h4>
      <p>At this stage, a simulation was created using Python. The process within the simulation included all data processing carried out in preparation for the training data. In addition, at this stage, logic was determined to decide when the push-up movement should be performed and when one repetition of the push-up movement had been completed. During the simulation development stage, debugging was also carried out to ensure that the program could run properly and produce the desired output and process. The simulation is tested on five different laptops using new video data showing people performing 10 to 15 repetitions of push-ups.</p>
</div>
