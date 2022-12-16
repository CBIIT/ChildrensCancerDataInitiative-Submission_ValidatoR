# ChildhoodCancerDataInitiative-Submission_ValidatoR.R
This takes a CCDI Metadata template file as input and creates an output file basesd on the QC checks.

This R Script takes a data file that is formatted to the [submission template for CCDI](https://github.com/CBIIT/ccdi-model/tree/main/metadata-manifest) as input. It will output a file that describes whether sections of the Metadata table PASS, ERROR or WARNING on the checks.

To run the script on a CCDI template, run the following command in a terminal where R is installed for help.

```
Rscript --vanilla CCDI-Submission_ValidatoR.R -h
```

```
Usage: CCDI-Submission_ValidatoR.R [options]

CCDI-Submission_ValidationR v1.0.0

Options:
	-f CHARACTER, --file=CHARACTER
		CCDI submission template workbook file (.xlsx, .tsv, .csv)

	-t CHARACTER, --template=CHARACTER
		CCDI dataset template file, can be the same Metadata template workbook file or a blank CCDI_submission_metadata_template.xlsx

	-h, --help
		Show this help message and exit
```

To test the script on one of the provided test files:

```
Rscript --vanilla CCDI-Submission_ValidatoR.R -f test_files/a_all_pass_CCDI_Submission_Template_v1.0.1.xlsx -t test_files/a_all_pass_CCDI_Submission_Template_v1.0.1.xlsx 
```

```
The data file is being validated at this time.

Process Complete.

The output file can be found here: ChildhoodCancerDataInitiative-Submission_ValidatoR.R/test_files/
```

`Note: The AWS bucket checks will not work with any of the test files, as the files and their locations are fake data`


|Message|Issue|Likely Fix|
|-------|-----|----------|
|ERROR: Please obtain a new data template with all sheets and columns present before making further edits to this one.|||
|WARNING: The following node, [node], did not contain any data except a linking value and type.|||
|ERROR: The following required columns are missing in this template:|||
|ERROR: For the node, [node], values still need to be generated for the required property, [required_property]|||
|ERROR: There is a missing value for the node, [node], in the required property, [required_property], on row: [row]|||
|ERROR: For the node, [node] there are missing required columns:|||
|ERROR: For the node, [node], leading/trailing white space was found in the property, [property], on row: [row]|||
|ERROR: The following ID, [id], has an illegal character (acceptable: A-z,0-9,_,.,-,@,#) in the property, [property]|||
|ERROR: [property] property contains a value that is not recognized: [value]|||
|ERROR: The following node, [node], has multiple instances of the same key value, which should be unique, in the property, [key_value]|||
|ERROR: The following node, [node], has no key values in the property, [key_value]|||
|ERROR: The library_id, [library_id], has multiple samples associated with it|||
|WARNING: The sample, [sample_id], has multiple single sample files associated with it.|||
|WARNING: The following file, [file_name], is found multiple times.|||
|ERROR: There are multiple samples associated with the single sample file, [file_name].|||
|WARNING: There are multiple url locations associated with the file, [file_name].|||
|WARNING: The file, [file_name], is not expected to have a [sequencing metric] value.|||
|ERROR: The file, [file_name], is missing at least one expected value (bases, avg_read_length, coverage, number_of_reads) that is associated with an SRA submission.|||
|WARNING: The file in row [row], has a size value of 0. Please make sure that this is a correct value for the file.|||
|ERROR: The file in row [row_pos], has a md5sum value that does not follow the md5sum regular expression.|||
|WARNING: There is more than one aws bucket that is associated with this metadata file in the, [node], node: [bucket].|||
|ERROR: The following file does not have the same file size found in the AWS bucket|||
|ERROR: The following file is not found in the AWS bucket|||
|ERROR: The following file is found in the AWS bucket and not the manifest that was provided|||
|WARNING: For the node, [node], there are multiple links on row: [row]|||
|ERROR: For the node, [node], the following linking property, [link_property], has a value that is not found in the parent node: |||

