# COLOR-BASED-FRUIT-RECOGNITION
## Introduction
This project is a Matlab program that detects which kind of fruit is in an image. From one image of a fruit, through a mask, a threshold and the mean of the RGB components of the color, the function can distinguish between some of them. The result is the type of the selected fruit. We worked with apples, tangerines, bananas, strawberries and pears. 

## Behavior

We start creating a matrix, that we will call alphabet, whose rows are the mean RGB values of each fruit. In order to do that, we design two functions: The first one, “createalphabet”, that loads fruit by fruit, using a for loop, all the pre-stored images and using the second function, “RGB_vec”, it gets the mean RGB vector of each type of fruit.
For getting this last vector, we process each image, maximizing their contrast and applying a mask (using the Otsu method with the function graythresh) that turns the white background into black (RGB= (0,0,0)). Using this technique, we isolate the RGB components of the fruit, so we can get them with exactitude. As the mask doesn't work perfectly, it creates some spots into the fruit that we were able to fill using the matlab function “imfill”. Once we have analyzed all the pre-stored photos of a type of fruit we compute its mean, getting the final vector, and we repeat this procedure with another group.
To recognize what kind of fruit is in an image introduced by a user, we create the function “WhichFruit”. First, we get the RGB vector of the unidentified fruit, using again the function “RGB_vec”, and we calculate the norm of the difference between the new RGB vector and, one by one, the mean RGB vectors of each fruit stored in the alphabet. Finally, the function displays what is the unidentified fruit. 
The last function creates the confusion matrix, a matrix having as rows the class of image that we use as input and as columns the class that the program assigns to the image. So, the matrix should be a diagonal matrix of threes in the perfect case. In our project, taking the tree first images of each class as reference for the alphabet and scanning the three last images of each class for creating the confusion matrix we got a perfect matrix:

	
##Limits
	
Our project uses mainly a color based algorithm to detect the fruit. Therefore, there is a certain degree of confusion and error when different fruits have the same colors. For example a red apple and a strawberry. That is due to the fact that there is no shape detection or analysis in our program. 
Another limit for our program is the background. Our project is designed exclusively for the detection of fruits in images with a white or almost white background. So any type of colors or distortions in it would eventually cause an wrong detection (wrong fruit type) within our program.  


## Possible applications
There are multiple applications for a program like this. One of the most beneficial applications would be in the industrial domain. For example an automatic sorting machine that can sort fruits based on their type using our program’s detection feature. In addition to that, with a little adjustment to our program, it could be used as the software of an automatic quality sorting machine that can detect low quality or unripe fruits or vegetables based on the different color spots (for example: green or black spots in a tomato).

