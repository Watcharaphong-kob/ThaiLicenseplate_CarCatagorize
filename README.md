# License Plate initial Character Analysis for Vehicle Categorization
## License Plate Recognition
![Screenshot 2024-03-13 170111](https://github.com/Watcharaphong-kob/ThaiLicenseplate_CarCatagorize/assets/81470950/a705a9b0-28ca-4f62-95cb-5449993ac3b5)

We applied the cv2 for license plate recognition. The key is to use the contour to select the license plate and its position then pick it out by using perspective transformation to transform it to the correct plate size. We add the cropping images to determine the region of interest, the filters for adjusting the video to control the noise and edge detection, and the threshold for the contour. By appropriately adjusting values for threshold, kernels, and classification criteria, we can locate the license plates on the cars even if moving. The located license plates will be extracted and collected in a folder for the next process.
## Character Segmentation
![Screenshot 2024-03-13 171325](https://github.com/Watcharaphong-kob/ThaiLicenseplate_CarCatagorize/assets/81470950/983068b9-6a89-4879-a818-e9a241c68721)

We utilize the EasyOCR library for character segmentation, a crucial step in text extraction from images. Utilizing deep learning models, such as convolutional neural networks (CNNs) and  recurrent neural networks (RNNs), EasyOCR processes images containing Thai text to detect individual characters. The library segments characters, identifies boundaries, and recognizes specific characters. 
In the context of car license plate images captured from recognition systems, EasyOCR accurately analyzes and extracts Thai text and numbers from license plates.
## Vehicle Categorization
![Screenshot 2024-03-13 171230](https://github.com/Watcharaphong-kob/ThaiLicenseplate_CarCatagorize/assets/81470950/e80bdfa0-1e00-4a01-b92d-9fb84e17d34a)

Vehicle categorization is the practice of classifying cars into various groups. In this context, we use data from initial character in license plates to classify vehicles. The method involves checking several characteristics on the license plates, such as the existence of specified symbols, numerals, or Thai language letters. 
This classification procedure can be beneficial for a variety of applications, including traffic management, automobile registration, and market research. Finally, it gives an organized approach to understanding and categorizing the many types of cars on the road. 


# How to use this program
In this program, we've chosen to separate it into three distinct pieces of code. This decision was made because when attempting to combine them, the system experienced significant slowdowns and generated numerous errors within the program.
## License plate Detection
We applied the cv2 library for license plate recognition. The key is to utilize contours to select the license plate and determine its position. Subsequently, we employ perspective transformation to resize it to the correct plate dimensions. You can gain a clearer understanding of this process by viewing the explanation provided in the attached clip below.
> [!IMPORTANT]
>   - [Video source (Download then play)](https://shorturl.at/ozHZ5(url))
>   - [License plate output](https://shorturl.at/lrAX2(url))
>   - [Video process](https://www.youtube.com/watch?v=JHHD-xioxbU(url))
>   - [Code explaination](https://www.youtube.com/watch?v=EIdgbmkKViU(url))
## Character Segmentation
> [!TIP]
> your environment should have Opencv, numpy, pandas, easyocr library

In the import section, if you're utilizing your own device (Windows), it's essential to include the following code snippet:
```
import os
os.environ['KMP_DUPLICATE_LIB_OK']='True'
```
In part of file path setting you should change your correctly path of directory
```
excel_filename = r"YOUR_DIRECTORY_PATH\YOUR_OUTPUT_EXCEL_FILE_NAME.xlsx"
photo_directory = r"YOUR_DIRECTORY_PATH_TO_THE_PICTURE"
```
> [!TIP]
> if you use the colab you should remove the r"" and change into 'path'

## Vehicle catagorization
In part of file path setting you should change your correctly path of directory
```
input_file_path = r'PATH_TOYOUR_EXCEL_DATA'
output_summary_file_path = r'PATH_TO_YOUR_DIRECTORY_FOR_SAVE_OUTPUT_FILE\OUTPUT_FILE_NAME.xlsx'
```
