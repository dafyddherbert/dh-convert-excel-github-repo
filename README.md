# Convert Excel Files to CSV with OIC + Oracle Functions

This repository hosts the code required to setup an Oracle Function that will convert Excel files in xlsx and xls to CSV. It also stores the artefacts required to create an Oracle Integration (OIC) flow that will call this function to perform Excel to CSV file conversion. 

This code is accompanied by a blog article, available here: 
- XXXXX

**Function Artefacts**

- [requirements.txt](requirements.txt) specifies the dependencies of the Excel2CSV conversion function
- [func.yaml](func.yaml) contains metadata about the function and declares associated properties
- [func.py](func.py) contains the Python function that converts a single Excel file to a CSV

sample file to call the function:
- [request.json](request.json)

to invoke the above function store the sample request in function folder within Cloud Shell and run:

  `fn invoke stv_FN_Demo convertexcelfiles < request2.json`
  
 Limitation: 
 - multiple worksheets are not supported

**Oracle Integration (OIC) Artefacts**

- [EXCELDEMO_PART1_01.00.0003.iar](EXCELDEMO_PART1_01.00.0003.iar) contains a sample integration that will thiger the above function 
- [CSV_example_1000.csv](CSV_example_1000.csv) is used in the above integration to define the shema for the stage read operation

Sample files: 

Feel free to replace these with anything you like but update the stage read schema definition in the integration:
- [SourceAPFile-20201116.xlsx](SourceAPFile-20201116.xlsx) & [SourceAPFile-20201117.xls](SourceAPFile-20201117.xls)


**Note: This code is only intended to be used for demonstration purposes to showcase the capabilities of OIC and related OCI services**__
