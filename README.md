# **Team Seven Nation Army**
## This is our solution to the Amazon ML Challenge 2024 !

### Problem Statement :
In this hackathon, the goal is to create a machine learning model that extracts entity values from images. This capability is crucial in fields like healthcare, e-commerce, and content moderation, where precise product information is vital. As digital marketplaces expand, many products lack detailed textual descriptions, making it essential to obtain key details directly from images. These images provide important information such as weight, volume, voltage, wattage, dimensions, and many more, which are critical for digital stores

### Output Format:
The output file should be a CSV with 2 columns:
index: The unique identifier (ID) of the data sample. Note that the index should match the test record index.
prediction: A string which should have the following format: “x unit” where x is a float number in standard formatting and unit is one of the allowed units (allowed units are mentioned in the Appendix). The two values should be concatenated and have a space between them.
For example: “2 gram”, “12.5 centimetre”, “2.56 ounce” are valid.
Invalid cases: “2 gms”, “60 ounce/1.7 kilogram”, “2.2e2 kilogram”, etc.
Note: Make sure to output a prediction for all indices. If no value is found in the image for any test sample, return an empty string, i.e., “”. If you have less/more number of output samples in the output file as compared to test.csv, your output won’t be evaluated.

### Approach : 
1) We used openCV, Pillow, etc. for image pre-processing.
2) Then applied pytesseract on the pre-processed image for OCR Recognition via ML Algorithms.
3) Then rotated each image in 4 direction and applied OCR to detect the text in aligned in all directions.
4) Then build the full unit mappings which can possibly be present in the image's OCR Text.
5) Then build our RegEx System to catch the patterns such that it catches words with specified units in unit mappings and the numerical values associated with it.
6) Defined cases for range type values and discrete values.
7) For maximum_weight_recognitionn and item_weight differentiation, we used appropriate keywords like 'for', 'upto', etc.
8) The complex part was length, width & height because they have same units, so, we applied our logic via max. and min. values to differentiate.
9) Then finally, predicted the answer and reversed mapped the units to their appropriate formats and put them in the final test_output.csv file.

### Result : 
--> As we know, we have a limitation to the computational power and storage, so, we could only apply these processes upto 15k images out of total 2.5 lac images and saved the ocr_text in test_15k.csv
--> And predicted the answers and presented them in test_15k_output.csv

Thank You 
