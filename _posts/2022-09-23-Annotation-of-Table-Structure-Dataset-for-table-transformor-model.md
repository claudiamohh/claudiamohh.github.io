## Annotation of Table Structure Dataset for microsoft/table-transformer Model

In this project, I had to annotate a custom table structure dataset that was used to train the table-transformer model by Microsoft. The tasks of the table-transformer model by Microsoft is to do:  
  1. Table detection (TD), locates the table
  2. Table structure recognition (TSR), recognizes the structure of a table in terms of rows, columns, and cells
  3. Functional analysis (FA), which recognizes the keys and values of the table. 
 
![image](https://user-images.githubusercontent.com/107597583/193000041-1cfae44b-cfaa-4f36-8f38-6a464cdaebc4.png)

Microsoft has also provided the pre-trained models for table detection and table structure recognition trained for 20 epochs. More information can be found in Microsoft's Github Repository: [table-transformer](https://github.com/microsoft/table-transformer). 

---
I started off by using Prodigy interface, shown below, to annotate different table components (e.g., tables, rows, columns, etc.) on PDF files. 

![image](https://user-images.githubusercontent.com/107597583/192675101-f39bca5a-9fce-42aa-84a9-2b20b707f0ec.png)

Visualisation of the annotated labels are shown below:

![Screenshot 2022-08-22 at 2 41 07 PM](https://user-images.githubusercontent.com/107597583/192674214-f128e6cf-8ee7-4028-8e24-5a1f5df4f004.png)

There are a total of 7 labels, 6 labels shown in the image above and an additional label 'no objects'. 
Further explanation of the labels:
  - 'table': Contains only table content, not including title and description of the table. It can be overlapped by other labels. 
  - 'table column': Must be interconnected with each other (left to right).
  - 'table row': Must be interconnected with each other (top to bottom).
  - 'table column header': Header of the table only, in special cases it contains multiple rows.
  - 'table projected row header': Subheaders in the table. 
  - 'table spanning cell': Cell that spans across several rows or columns, can cover multiple rows or columns. 
  - 'no object'
   
Additionally, there was an additional label 'crop' that is not in the table-transformer model by Microsoft. The purpose of this label is to crop the image which  contains the table title, table description, table footnote and table content. This will then be the input of the table structure model. 

While annotating the files, I documented certain tedious and confusing cases which can be found here [Handshakes Internal Jira Ticket](https://handshakesbydc.atlassian.net/browse/AI-335). An example of a confusing case is shown below. 

![image](https://user-images.githubusercontent.com/107597583/193007211-3df74dd7-221e-4e68-b182-246027295f91.png)

There are overlapping contents in the yellow and turqoise bounding boxes, where the yellow bounding box should only contain table row header and the turqoise bounding box should only contain numerical values for this table. In the third last row, 'Exceptional item included in Depreciation, amortisation and impairments' fall under the first and second column. 

After annotating the pdf files, I proceeded to convert the prodigy annotations jsonl files to xml files and work on table detection to locate tables. 
 
Visualisation of the converted XML is shown below, where the table is in the green bounding box. 
![image](https://user-images.githubusercontent.com/107597583/192673497-a712a56b-d06e-400d-8379-9de73848e536.png)

In addition to those above, I have learned to test my codes using unittests, defining the code’s intent more precisely and have a more decoupled architecture. 

---
Learning points from this project: 
- Learned to annotate dataset correctly
- Learned to write and test unittests  
- Learned to convert jsonl files to xml files
