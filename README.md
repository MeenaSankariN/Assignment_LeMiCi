Data preprocessing pipeline

Food recommendation system: 

This dataset which was prepared by our college food department and the client gave in format of a Microsoft word which contained 5 columns- Id, food name, description, state and respective image for each food. It was converted into a csv file containing all 355 food items to 355 rows of pure text data with the image embedding taggingIDs too. Initially I had only the columns from the original dataset, late I added manually some more columns- veg_nonveg, taste, course_type, region and texture for more information clarity. There were some duplicates with different spellings like- Chola Bhatura or Chole Bhature and so I have directly changed it in the dataset since I experimented many times with the model and changed accordingly each time. This is my current project that I am working on with my guide and so some of the basic preprocessing steps have been done to the master file as it is a small dataset.

In this code file, I have loaded the dataset, defined 2 functions for normalization, prompting templates, generating prompt answer pairs for training and validation and finally the main function which actually integrates all the above functions to create two Jason files- train and val. The dataset is of 355 rows and i have given 8 prompt templates. So a total of 2840 prompt answer pairs would be generated where 284 (10%) would be validation Jason file and 2556 (90%) would be for training. Finally everything is executed under the main function.

Normalization: This function is currently not required for my data as it is already 60% clean except the upper case of the words and may be some unwanted space between. But this function is definitely needed in this pipeline if we are changing or manipulating the dataset for future extension. Reproducibility and reusability is essential when it comes to real time data and models.

Prompting: NLP models are basically designed for learning, understanding and responding through human language. So, even though our dataset is in csv format which is for reading and storing purpose, a proper sentence or a sequence of sentences with correct context and the same dataset should be available for the LLM/SLM/MiniLM to learn and reproduce according to human's prompt. NLP models learn the natural language format data and so prompting questions and its answers are necessary. 

Train/val split: All the 355 datasets will get 8 prompts along with their answers as a pair. Splitting is done after prompt generation. From these 2840 prompt/answer pairs, 10% would be taken as validations pairs and rest would be used for training purpose. 

