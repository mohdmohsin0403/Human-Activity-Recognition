# Human-Activity-Recognition

The [Dataset](https://drive.google.com/file/d/1Z8D_o22h7Bu4A_PlPp5v_K25bmiSWEST/view?usp=sharing) is shared via link and also been released.

Ever wondered how your smartphone responds to the motion of your body while playing your favorite game, or maybe watching a 360-degree picture on it? What is that under the hood that makes this happen?

Apart from supporting advanced gaming, accelerometers and gyroscopes have many other applications. One such application is Human Activity Recognition(HAR), using data collected from an accelerometer of a smartphone. This information can be further consumed by health and fitness monitoring applications.

In this, we are going to employ Long short-term memory (LSTM), an artificial recurrent neural network architecture for the human activity recognition task, which will learn complex features automatically from the raw accelerometer signal to be able to differentiate between common human activities.

## About the Data

Smartphones contains the tri-axial accelerometers that measure acceleration in all three spatial dimensions. In this, we shall be using the raw accelerometer signal data sourced from WISDM Lab, Department of Computer & Information Science, Fordham University, NY.

It contains the data collected from 36 users as thy perform different activities. The glimpse of the dataset is given below:
![1-har](https://user-images.githubusercontent.com/78999231/195382874-8b59fe38-4e27-4ed0-a102-443aa4a69905.png)

Here we can see, there are n-number of rows, so, before processing we will clean our dataset.

### Data Cleaning and Processing

First we will drop the null values and then will change datatype of the ‘z-axis’ column to float. Then, we will drop the rows where the timestamp = 0 and sort data in ascending order of ‘user’ and ‘timestamp’ columns.

After sorting, the dataset is sorted and looks like:
![2-gar](https://user-images.githubusercontent.com/78999231/195384219-a52d0789-397e-4607-af29-709a4cf0d463.png)

### Analysing the data

![WhatsApp Image 2022-10-12 at 20 59 40](https://user-images.githubusercontent.com/78999231/195385147-2078c335-7347-4e48-a01d-ff0a6cccfbdc.jpeg)

After, analysing the that there is a imbalance in the dataset.

Now let’s see how the individual users are contributing to each activity. Here is the glimpse shown below:
![image](https://user-images.githubusercontent.com/78999231/195385847-af265c63-b779-4568-aede-296914c625fd.png)
By, the above graph we can see that all the users perform all the activities but the time they perform are different.

We will now visualize how the signal values in each of the x, y, and z dimensions vary with time.
![image](https://user-images.githubusercontent.com/78999231/195386489-76672330-eb6d-4a24-9989-38fd40f703c0.png)
![image](https://user-images.githubusercontent.com/78999231/195386573-4456408d-cae5-4d21-a18f-d9a7ce08772b.png)
![image](https://user-images.githubusercontent.com/78999231/195386720-2b45081e-f0f2-4e84-9aaf-bc396add2219.png)
![image](https://user-images.githubusercontent.com/78999231/195386846-fbc1e6e2-9b19-46dc-abf1-1bde30dee262.png)
![image](https://user-images.githubusercontent.com/78999231/195387013-5cad67b7-6cf9-4e72-9433-627381264951.png)
![image](https://user-images.githubusercontent.com/78999231/195387107-0f4bad48-9c7a-46ab-a2b3-4d8400b4f183.png)

### Preparig Data

![image](https://user-images.githubusercontent.com/78999231/195387547-4be4c362-fe5e-43b8-9145-9eeb3ddeb247.png)
The data is being prepared.

### Building Model Architecture

Here is the summary of the model.
![image](https://user-images.githubusercontent.com/78999231/195387924-068c5971-e2fa-420b-8efe-a96a8ce85987.png)

### Model Training, Evaluation and Construction of Confusion Matrix

Model is trained, upto 50 epochs.
![image](https://user-images.githubusercontent.com/78999231/195388307-5095c514-cd39-4cbb-acf7-84cdb9cbff4b.png)

Now, training epoch is plotted and here is the screenshot for the same.
![image](https://user-images.githubusercontent.com/78999231/195388559-dec8497b-86c3-4bd9-bbb4-d1665d49f8ac.png)

The confusion is matrix is then created, and it can be clearly seen that 
![image](https://user-images.githubusercontent.com/78999231/195388921-1173f1da-8d28-4132-8b25-cdae6f1a464c.png)

Jogging and Walking are more preferred by the people & sitting and standing are the minor classes.
