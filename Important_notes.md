## How to add image in jupyter notebook 
**Adding image using link**<br>
<code>from IPython.display import Image
Image(url='https://i.imgur.com/aKcwkSx.png')</code>

**Adding file using file path**
1.The first step is to import the libraries that we need to display images in Jupyter Notebook. We will be using the Pillow library to read the image and the IPython.display library to display the image.<br>
2.The next step is to load the image that we want to display. We will use the Image.open() method from the Pillow library to load the image.<br>
3.We can display the image using the display() method from the IPython.display library.<br>
 Example Code:<br>
  <code>from PIL import Image
  from IPython.display import display
  img = Image.open('./assets/bricks.jpg')
  display(img)</code><br>
  This will display the image.
