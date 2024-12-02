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

**Resampling Time Series Data**
To convert our daily data into monthly data, we're going to use the .resample() function. The only things we need to specify is which column to use (i.e., our DATE column) and what kind of sample frequency we want (i.e., the "rule"). We want a monthly frequency, so we use 'M'.  If you ever need to resample a time series to a different frequency, you can find a list of different options. (for example 'Y' for yearly or 'T' for minute).<br>
After resampling, we need to figure out how the data should be treated. In our case, we want the last available price of the month - the price at month-end.<br>
1.	df_btc_monthly = df_btc_price.resample('M', on='DATE').last()<br>
If we wanted the average price over the course of the month, we could use something like:<br>
1.	df_btc_monthly = df_btc_price.resample('M', on='DATE').mean()<br>

 **To reverse the order of an array**
 you can either use the (double) colon operator  or use the built-in .flip() function. Either way works.
1.	np.flip(a)
or
1.	a[::-1]

