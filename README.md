# Non-Planar Camera Calibration

Program 1 performs feature extraction from an input picture based on 2D image points and corresponding 3D world points. Main purpose:
1. Generate chessboard features automatically using OpenCV
2. Manually select features through mouse click
<br/>

Program 2 performs non-planar camera calibration using the feature points provided in the input file (3D world points and corresponding 2D image points). Main purpose:
1. Non-planar Camera Calibration
2. Mean Square Error between known points and computed points
3. Random Sample Consensus (RANSAC) algorithm for projection matrix
4. Testing with different noise percentages
<br/>

Programs were implemented using Python and OpenCV. Refer the report for further implementation details, format of input files, and instructions to run the code:
<a href="https://github.com/chandnii7/CameraCalibration/blob/main/doc/Report_A4_Chandni_Patel.pdf">View Report</a>
<br/><br/>

### Results:
1. Input File Example:
<img src="https://github.com/chandnii7/CameraCalibration/blob/main/data/out1.jpg" height="200" width="350"/>
<br/>

2. Features Extracted:
<img src="https://github.com/chandnii7/CameraCalibration/blob/main/data/out.jpg" height="350" width="350"/>
<br/>

3. Non-planar Camara Calibration Example:
<img src="https://github.com/chandnii7/CameraCalibration/blob/main/data/out2.jpg" height="400" width="350"/>
<br/>

4. Non-planar Camara Calibration with RANSAC using noisy data Example:
<img src="https://github.com/chandnii7/CameraCalibration/blob/main/data/out3.jpg" height="400" width="350"/>
<br/>

5. For more noisy data, we get huge mean square error with RANSAC as it fails completely. This is because of 2 main reasons:
   * RANSAC does not work well with low inlier ratios as every point in the dataset gets a vote just for being in the model. This makes the model more robust towards outliers. So, we need more inliers and less outlier for RANSAC to work properly. It does not work well as especially when there are more than 50% outliers.
   * RANSAC is also not reliable when there are a lot of parameters to tune. Here, we have 12 parameters which makes it more complicated.



