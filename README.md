# Object-classification
Program to classify different objects

It's build from the face biometric project. For more insight visit that project.
This program is designed to identify different objects. 

I have created custom objects and custom images to train them. I have trained the network to identify bottles
and mobile. However, you can design for as many classes of objects as you like.

The work flow of the program:
You would first create the profile of the object by its name and then the profile would be created under the train and test
directory respectively. 
For capturing the object image you will give keep the name of the object (the name of the profile) in the first text field
and in the second give the alphabetical ordering of the new objects. say, ist obj: A, 2nd obj: B and so on. 
However, the alphabet named sequence shouldn't be repeated. You can even keep the name of the object followed by numbers such as
1st obj: obj1, 2nd obj: obj2.

After you have collected all the custom data then you would want to train the model. Be sure to collect the same number of samples for 
all the different objects. By default I have set it to 8 different sample by default. You can increase to as much as you want.
You can even record the different faces of the objects, but again the naming should be properly handled.

For the next session you wouldn't want to train again unless you have new objects to include. You would load the pretrained model
and then start detecting the objects.

The result of the objects would be shown in the Text area, and some of the raw computations and model descriptions would appear in
the terminal.

>>> Create a dataset directory, and training_set, test_set sub directories before executing the program. 
8 capture sessions should be there in total. If you want more, be sure to change here:

self.classifier.fit_generator(training_set,
								 steps_per_epoch = self.compute_files()*64,  ---> 8*n
								 epochs = 2,
								 validation_data = test_set,
								 validation_steps = self.compute_files()*16)  ---> 2*n
                 
                 
  >>>  n is the number of capture sessions for different objects.
