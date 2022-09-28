## Annotation of Table Structure Dataset for microsoft/table-transformer Model

My last project was to extract tables from pdf files. This project demands 3 smaller tasks:
  - table detection (TD), locates the table
  - table structure recognition (TSR), recognizes the structure of a table in terms of rows, columns, and cells
  - functional analysis (FA), which recognizes the keys and values of the table. 

I started off with annotating the pdf files using prodigy to study the different cases of each table in the pdf files. 
This annotation was important as it gave me a better idea on how to start and write scripts for the table transformer model to process. 

An example of how the annotation looks like:

![Screenshot 2022-08-22 at 2 41 07 PM](https://user-images.githubusercontent.com/107597583/192674214-f128e6cf-8ee7-4028-8e24-5a1f5df4f004.png)

![image](https://user-images.githubusercontent.com/107597583/192675101-f39bca5a-9fce-42aa-84a9-2b20b707f0ec.png)

There were some file that were tedious to annotate and those difficult cases can be found here: https://handshakesbydc.atlassian.net/browse/AI-335. 

After annotating the pdf files, I then proceeded to convert the prodigy annotations jsonl files to xml files. This is done to extract tables information only.  

![image](https://user-images.githubusercontent.com/107597583/192673459-e7c47c4f-bdaa-4ac4-8e53-2929631b3fe7.png) 

![image](https://user-images.githubusercontent.com/107597583/192673497-a712a56b-d06e-400d-8379-9de73848e536.png)

The first image is the original pdf while the second image is after detecting the tables. The tables are bounded by the green bounding boxes, which is the input of the table transformer model to return the tables. 

In addition to those above, I have also learned to write tests to test my codes, these tests help to define the code’s intent more precisely and have a more decoupled architecture. 

Learning points from this project: 
- Annotating dataset correctly
- Writing and testing unittests  
- Converting jsonl files to xml files
