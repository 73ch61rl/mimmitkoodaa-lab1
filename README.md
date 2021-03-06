# IBM Cloud :cloud: & Watson 
## Mimmitkoodaa workshop

# Create your own classifier using Watson Visual Recognition

<!--- GIF & images
![Alt Text](https://media.giphy.com/media/vFKqnCdLPNOKc/giphy.gif)
--->
 
## Introduction 
In this guide, we will create our own custom classifier classifier using Watson Visual Recognition API on IBM Cloud.

#### Prerequisites
- Register on IBM Cloud at https://bluemix.net


## Step 0. Explore: Visual Recognition Service
The IBM Watson™ Visual Recognition service uses deep learning algorithms to analyze images (.jpg, or .png) for scenes, objects, faces, and other content, and return keywords that provide information about that content. You can also create custom collections of your own images, and then upload an image to search the collection for similar images. 

![](/screenshots/Picture0.png?raw=true)

#### Use Cases 

| Industry | Use case example|
| ------------- |-------------|
| Manufacturing | Use images from a manufacturing setting to make sure products are being positioned correctly on an assembly line.|
| Visual Auditing| Look for visual compliance or deterioration, train custom classifiers to understand what defects look like.|
|Insurance | Rapidly process claims by using images to classify claims into categories.|
| Social Listening | Use images from your product line or your logo to track buzz about your company on social media. |
| Social Commerce | Use an image of a plated dish to find out which restaurant serves it and find reviews.| 
| Retail | Take a photo of your favorite outfit to find stores with those clothes in stock. |
| Education| Create image-based applications to educate about taxonomies, use pictures to find educational material or similar subjects.|

#### Demo
To see the Visual Recognition service in action, see the Visual Recognition demo app. With the demo, you can analyze images for subject matter, and faces, as well as train a temporal custom classifier.

https://visual-recognition-demo.ng.bluemix.net/ 

#### Explore the API (First go through the lab at least once) 
Interact with the Watson API to understand how it works. Use the explorer to test your calls to the API, and to view live responses from the server.   
http://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#apiexplorer 
OR
https://watson-api-explorer.mybluemix.net/apis/visual-recognition-v3#/ 

You can authenticate to the Visual Recognition API by providing the API key that is provided in the service credentials for the service instance that you want to use. After you create an instance of the Visual Recognition service, you can view the API key by selecting Service Credentials from the left pane of the service dashboard. 
You can do the training through the API explorer or using CURL if you prefer. 

#### Documentation 
Find the complete documentation on the Visual Recognition service here: http://www.ibm.com/watson/developercloud/doc/visual-recognition/ 

#### Other Watson services
Check other Watson services: http://www.ibm.com/watson/developercloud/doc/ 

Explore the APIs: https://watson-api-explorer.mybluemix.net/ 
 
 
## Step 1. Create your Visual Recognition service
1.	Click "Catalog" in the upper right corner and then find the Visual Recognition service at the bottom of the catalog under Watson category - (scroll down might be needed). 
Click on it to add it to your dashboard. 

![](/screenshots/Picture1.png?raw=true)
 
2.	Select the region and space where you want to deploy the service and click on 'Create'. The IBM Cloud Lite account only allows to create one visual recognition service per account, so if you already have a service in use go to Step 2.

![](/screenshots/Picture2.png?raw=true)
 
3.	After few seconds you will have your service ready to be used. 

## Step 2. Create and train your classifier
Once you have created the Visual recognition service it's time to start creating a new classifier. By default, the Visual recognition service will be able to detect all kind of objects, forms, colors and things in the images. The same way the demo application in Step 0 was able to detect. However, in this lab we will create our own classifier. 

A classifier can be premade or self-created and uses algorithms to classify a picture as an input. Before we enter the Visual Recognition tool we will need to generate an API key. Click on "Service credentials" on the left side menu. 

![](/screenshots/Picture3.png?raw=true)

Click on the "New Credential" button to generate an API key. 

![](/screenshots/Picture4.png?raw=true)
 
A window will be prompted, simply click on "Add". 

![](/screenshots/Picture5.png?raw=true)
 
Now that you have your credentials ready, copy the API key and save it in a notebook in your computer if you want, or keep the tab open. We will need that later in the lab. 

![](/screenshots/Picture6.png?raw=true)
 
Now let's access the Visual Recognition Tool by entering the following URL in a new tab:
 
 https://watson-visual-recognition.ng.bluemix.net/

Click on API Key and enter the credentials you copied in the previous stage.

![](/screenshots/Picture7.png?raw=true)
 
You will see 3 classifiers ready. This is the default Visual recognition set up, so in addition to the general classifier it is able to recognize food and faces. 

Let's create our own classifier by clicking in "Create Classifier".
 
 ![](/screenshots/Picture8.png?raw=true)
 
Once that's done download the training data located in the "training material" folder. Download the .zip files. As you can see we are going to train Watson to recognize Angry Birds characters. 

Name your classifier for example "AngryBirds" and create three classes named "Red", "Blue" and "Yellow". For the negative class you can use the Pigs.zip file.
Note that we are not recognizing colors, this is just the name of our category. 

Drag and drop the .zip files into their correct classes. Once that's done press "Create" as shown in the next picture. 

 ![](/screenshots/Picture9.png?raw=true)
 
The training process can take few minutes.

 ![](/screenshots/Picture10.png?raw=true)

 
#### Congrats! You've now created your own customized classifier in the Watson Visual Recognition service. 

Now drag and drop images to test how the classifier works. 

 ![](/screenshots/Picture10b.png?raw=true) 
 
 
 **Note: This example is using a very small amount of pictures so the results will not be too accurate.**
 
The API will accept as few as 10 per class, in this example we used ~20 per category,  but we strongly recommend using a significantly greater amount of images to improve the performance and accuracy of your classifier such as 100s or 1000s of images.


