# Deploying a Deep Learning Model for Weed Detection 
Code used to deploy the weed-detection model. This is a guide on how to deploy to a Hugging Face Space. You are ready to do so if you have already trained your deep learning model, have your inference logic written, and have obtained the production files (mine were obtained by building with vite).

### Step 1: Go to Hugging Face Spaces
Create an account if you haven't already
Then, click on create a new space

### Step 2:
Fill in the information, and choose the static space:
![image](https://github.com/user-attachments/assets/977871cc-e9f4-442c-bda7-33940ff4e9bc)

### Step 3:
- Choose the Files tab in the top right
- Click "+ Add File" button
- Choose Upload files
- Drag your production files directly into the upload area (essentially when you run your build command, it should bundle your application and output the files to a folder. In my case, it was my _dist_ folder.)
- Make sure your **index.html** file is located in the **root** of your hugging face repository. The new one you upload will replace the placeholder. You should be able to just select all of the files in _dist_ and drag them for the correct file structure
- Select "Commit changes to main"

### Step 4:
Ensure that both your model and .js and .css files are now in the repo. 
![image](https://github.com/user-attachments/assets/62d42045-02e8-4a5f-a61f-54ac8c15f088)
In this image, my model and shards are in the best_web_model folder, and my index.js and index.css files are in the assets folder

### Step 5:
Check the paths to make sure your script file (.js) and stylesheet (.css) are at the correct filepaths. I had to modify mine to remove my original github repository name from the path:
![image](https://github.com/user-attachments/assets/c94b6296-58b0-4689-a83a-d2be88764b9e)

### Step 6:
You should be able to switch from Files to App and see your deployed model at https://huggingface.co/spaces/<your-username>/<your-space-name>. 


#### Note: 
If you are still having trouble with loading your model, most likely the path for your model is incorrect. In your actual index.js file, make sure you have the model path set to the structure of your hugging face repository. Use the relative path.
In my case, I have ./best_web_model/model.json to get my model:
![image](https://github.com/user-attachments/assets/323bf411-8ed3-4311-a652-0f5db5556acc)

After these changes, make sure to build your development files again and upload your modified files to hugging face, ensuring that you correct any paths in index.html. Check the deployment again, and it should work if the paths are all correct!



