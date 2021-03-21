# Where's Waldo

## Usage
The program can be access via Jupyter Notebook. The file `Where is Waldo.ipynb` contains all the necessary code required to run the program.<br/> 

To use the program 2 image files will need to be provided. The first is a ***Source Image*** which is the puzzle you wish to solve. The second is a ***Template*** which is the target image that is to be located inside the Source Image.

***Example Source Image***  
![puzzle1](https://user-images.githubusercontent.com/78133830/111909772-2cb6ca80-8a91-11eb-8b5b-57e90b82cb06.jpg)

***Example Template***  
![the man himself](https://user-images.githubusercontent.com/78133830/111909794-3dffd700-8a91-11eb-845c-565e01a3d738.png)


## Method

Template Matching is the idea of sliding a target image(template) over a source image (input). The template is compared to the input. A match is determined by the how much the neighbouring pixels in the input matches with the template.

Using Python's OpenCV library, we can implement Template Matching. OpenCV supports various methods to calculate similarity, for this project we used `TM.CCOEFF_NORMED`
![1_MouMPPYnxm6sLIS971lMqw](https://user-images.githubusercontent.com/78133830/111910418-de56fb00-8a93-11eb-8be9-28ef3ee244e7.png)

The template patch is slid over the input with this matrix and it determines a score that will indicate whether there is a match. TM_CCOEFF_NORMED finds the average value of the template and matches it to the average of the input. A score of 1 is a perfect match, -1 is a bad match and 0 is neutral.
