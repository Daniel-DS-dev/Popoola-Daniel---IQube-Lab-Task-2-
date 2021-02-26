# Popoola-Daniel---iQube-Lab-Task-2-

* This is my solution to the iQube Lab's Task 2

## How many faces?
You are provided with images of people at meetings, gatherings, group photos, etc. Count the number of faces you can spot in each image. There will be no more than 15 faces in each of the images. Assume that half or more of each face will be visible.
Here are the first three images corresponding to the 3 sample test cases which will be provided

Input Format:
The first line of input will contain two integers, R  and C, representing the number of rows and columns of image pixels, respectively.
A 2D grid of pixel values will be provided (in regular text format through STDIN) that represents the pixel-wise values from the images. The images were originally in JPG or PNG formats.
Each pixel will be represented by three comma-separated values denoting the Blue, Green, and Red components, respectively. The pixel values will be in the range 0 to 255. There will be a space between consecutive pixels in the same row.

No input test case exceeds 15MB in size, most are within 5MB and many are less than 1MB. So you may gradually iterate on your solution to handle larger and more complex cases. Take care to account for very different kinds of faces!
Output Format
Output a single integer, the number of faces spotted in the provided image.


## Solution
### Discuss in detail how you solved the problem.
* The task is to count the number of faces in particular images, I was provided with 3 images that have been converted to 2D grids of pixel values. The 2D grid of pixel value of each image was provided in seperate text files.
* To count the number of faces in each image, I had to first convert each image back to it's image form or array form before it can be usable on any deep learning or machine learning model.
* The first thing I did was to read in the image data of each image into my notebook, using Python's function, 'open()'. Using this function, I read in image data from each text file line by line. I created 3 different lists for each image data named: 'img1', 'img2' and 'img3'.


* The image data I read in was read in regular text format, so I had to convert it back into it's original image format (The images were originally in JPG or PNG formats). Then I will build a model to detect the number of faces in each image.
* I will read the text document in line by line, and store them in seperate lists, then I will write a function to clean each image data. 


* The image data of each image are stored in three different text files named: 'input00.txt', input01.txt' and 'input02.txt'
* I will read-in each text document line by line, and store them in different lists
* I will use Python's 'open()' function to open each file, and access it's content 
* **NOTE**: The text files are in a folder named 'input', so I have to include the full file path for each text document to be able to read in the text document into my notebook.


* After reading in the image data using the open() function, the data type of all the values in each image data was of type string, and my lists contained unwanted spaces that were read in with the data. Also the first line in each text file had the dimension of the image, so I had to remove that from the list also. So I had to do some cleaning.

* For example in the first image data read in from the file, 'input00', the first line contains the dimension of the first image, followed by space indicated by '\n' then the second line contains pixel values of the first row in the image data.
* Each pixel will be represented by three comma-separated values denoting the Blue, Green, and Red components, respectively
* So we can see the first pixel is '2, 6, 184', and the last pixel is '1, 10, 151', and then another space ('\n')
* The first file has 418 rows and has 870 pixels per row, the second image has 173 rows and 291 pixels per row, and the third image contains 288 rows and 460 pixels per row


* I then removed the first line of each list, and stored them in seperate lists, so my image data lists now had only the pixel values of their image.
* Then I cleaned up each image data, and stored each cleaned data in a numpy array in a format that can be viewed as an image.
* The final image array of each image will be a rank3 array, which will have a shape in the form of (x1, x2, 3)
* Where x1 = number of rows
      * x2 = number of columns, or number of pixels per row in each image and
       * 3 is the number of color channels in our array.
* E.g. the shape of the first image after cleaning should be (418, 870, 3)
* To get a rank3 array from a list, the list has to have 2 nested lists within it. (a list of lists of lists)

* Since our data was read-in in string format, All the pixels in each row of our image data is stored as a string value which contains pixels seperated by a space as a delimiter. i.e. for row 1 in image 1 we have '2, 6, 184 .... 1, 10, 151'
* Remember, each pixel is represented by three comma-separated values denoting the Blue, Green, and Red components (3 colour channels) respectively. The first pixel in the first row of the first image is '2,6,184'
* I needed to store each pixel in it's own list, and then each row will contain all the pixels in that row in a single list, and then all the rows in that image will be stored in another single list.
E.g. The first image has 418 rows, and 870 pixels per row. Each 870 pixels per row will stored in seperate lists i.e. we will have 870 lists in each row, and then each 418 rows containing 870 lists each which will be stored in a single list. And that way we have a list of lists (418 lists) of lists(870 lists). i.e. the first row of the first image should look like: [[2, 6, 184] ... [1, 10, 151]]
