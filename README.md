# Samples for the Adobe PDFTools Extract Python SDK

This sample project helps you get started with the PDFTools extract SDK.

The sample classes illustrate how to perform PDF-related extraction (extracting content of PDF in user friendly 
structured format) using the SDK.

## [Internal] Pointing to Stage or Develop

https://wiki.corp.adobe.com/display/DEX/Java+SDK


## Prerequisites

Before installing the sample:

* Install Python from [https://www.python.org/](https://www.python.org/). We've tested the code with Python 3.6, but any Python 3.x version should work. If your code base is running under Python 2.7, you may find it helpful to use the [3to2](https://pypi.python.org/pypi/3to2) tools to port the code to Python 2.7.

## Authentication Setup

The api credentials file and corresponding private key file for the samples is ```pdftools-api-credentials.json``` and ```private.key``` 
respectively. Before the samples can be run, replace both the files with the ones present in the zip file received 
via [Beta Program Access](https://opensource.adobe.com/pdftools-sdk-docs/beta/extract/#beta-program-access) workflow.

The SDK also supports providing the authentication credentials at runtime, without storing them in a config file. Please
refer this [section](#extract-text-elements-by-providing-in-memory-authentication-credentials) to 
know more.

## Installation

Follow these steps to install the samples:

1. Clone the repo, using one of these commands:
    [Internal]* ```git clone git@git.corp.adobe.com:dc/dc-extract-sdk-python-samples.git```

2. Create and activate a virtual environment (optional). If you're new to Python virtual environments, [Miniconda](https://conda.io/miniconda.html) is a great place to start.
3. In the root folder of your cloned repo, install the dependencies for the sample as listed in the ```requirements.txt``` file with this command: ```pip install -r requirements.txt```.

## A Note on Logging
For logging, this SDK uses the logging module(https://docs.python.org/3/library/logging.html). The logging configurations 
are provided in ```logging.yaml```.

## Structured Information Output Format
The output of SDK extract operation is Zip package. The Zip package consists of following:

* The structuredData.json file with the extracted content & PDF element structure. See the [JSON schema](https://opensource.adobe.com/pdftools-sdk-docs/shared/extractJSONOutputSchema.json). 
* A renditions folder(s) containing renditions for each element type selected as input. 
  The folder name is either “tables” or “figures” depending on your specified element type. 
  Each folder contains renditions with filenames that correspond to the element information in the JSON file. 


## Running the samples
The following sub-sections describe how to run the samples. Prior to running the samples, check that the credentials 
file is set up as described above and that the project has been built.

The code itself is in the ```sample``` folder. Test files used by the samples can be found in ```resources/```. When executed, all samples create an ```output``` 
child folder under the working directory to store their results.

### Extract PDF Elements from PDF Document
These samples illustrate how to extract PDF elements from PDF. Refer to the documentation of [ExtractPDFOperation.java](https://opensource.adobe.com/pdftools-extract-java-sdk-samples/apidocs/com/adobe/platform/operation/pdfops/ExtractPDFOperation.html)
to see the list of inputs.



#### Extract Text Elements

The sample class extract_txt_from_pdf.py extracts text elements from PDF Document.

```$xslt
python sample/extract_txt_from_pdf.py
```

#### Extract Text, Table Elements

The sample class extract_txt_table_info_from_pdf.py extracts text, table elements from PDF Document. 

```$xslt
python sample/extract_txt_table_info_from_pdf.py
```
#### Extract Text, Table Elements with Renditions of Table Elements

The sample class extract_txt_table_info_with_rendition_from_pdf.py extracts text, table elements along with table renditions
from PDF Document. Note that the output is a zip containing the structured information along with renditions as described
in [section](#structured-information-output-format).

```$xslt
python sample/extract_txt_table_info_with_rendition_from_pdf.py
```
#### Extract Text, Table Elements with Renditions of Figure, Table Elements

The sample class extract_txt_table_info_with_figure_tables_rendition_from_pdf.py extracts text, table elements along with figure 
and table element's renditions from PDF Document. Note that the output is a zip containing the structured information 
along with renditions as described in [section](#structured-information-output-format).

```$xslt
python sample/extract_txt_table_info_with_figure_tables_rendition_from_pdf.py
```

#### Extract Text Elements (By providing in-memory Authentication credentials)

The sample class extract_txt_from_pdf_with_in_memory_auth_credentials.py extracts text elements from PDF Document. 
This sample highlights how to provide in-memory auth credentials for performing an operation. 
This enables the clients to fetch the credentials from a secret server during runtime, instead of storing them in a file.

```$xslt
python sample/extract_txt_from_pdf_with_in_memory_auth_credentials.py
```

#### Extract Text Elements and bounding boxes for Characters present in text blocks

The sample class extract_txt_with_char_bounds_from_pdf.py extracts text elements and bounding boxes for characters present in text blocks. 
Note that the output is a zip containing the structured information 
along with renditions as described in [section](#structured-information-output-format).

```$xslt
python sample/extract_txt_with_char_bounds_from_pdf.py
```

#### Extract Text, Table Elements and bounding boxes for Characters present in text blocks with Renditions of Table Elements

The sample class extract_txt_table_info_with_char_bounds_from_pdf.py extracts text, table elements, bounding boxes for characters present in text blocks and table element's renditions from PDF Document. 
Note that the output is a zip containing the structured information 
along with renditions as described in [section](#structured-information-output-format).

```$xslt
python sample/extract_txt_table_info_with_char_bounds_from_pdf.py
```

#### Extract Text, Table Elements with Renditions and CSV's of Table Elements

The sample class extract_txt_table_info_with_table_structure_from_pdf.py extracts text, table elements, table structures as CSV and table element's renditions from PDF Document.  
Note that the output is a zip containing the structured information 
along with renditions as described in [section](#structured-information-output-format).

```$xslt
python sample/extract_txt_table_info_with_table_structure_from_pdf.py
```

### Contributing

Contributions are welcome! Read the [Contributing Guide](.github/CONTRIBUTING.md) for more information.

### Licensing

This project is licensed under the Apache2 License. See [LICENSE](LICENSE.md) for more information.