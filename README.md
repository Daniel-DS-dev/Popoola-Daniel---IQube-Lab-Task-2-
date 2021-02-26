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

