# sratoolkit_datamining
repo for data mining application with sratoolkit


# presentation captions
Hi,
My name is Jose Oviedo, and today I'll be discussing the data collection aspect of the data mining pipeline through open-data mining with a focus on applying it to the field of genomics. I'll briefly explore the background of why we might consider using open-data and the potential benefits, such as ability for conducting novel studies or investigations that can answer new questions by using existing datasets, or by combining them with external data to create new datasets.

Data mining is applicable across various fields that rely on data. However, as mentioned I'll be focusing on the field of genomics, particularly on the data collection and pre-processing of DNA sequencing data, which is essential for downstream analyses.

The data mining application we will perform addresses a real-world use case that could arise, and it’s also relative to what we learned in the course regarding implementing new or “new-to-you” practical software applications, and just continually expanding our knowledge of available domain relative software packages.

The relatively recent increase of accessible open-data for research purposes has created new possibilities for research using existing datasets in novel ways as mentioned and this publication I found supports that conclusion to some degree. 

One way to utilize open-data in this context is to cite and source sequencing data from the Sequence Read Archive (SRA) repository related to the sub-field of genomics you are investigating and use that data in some way to enhance the current project dataset.
The SRA is the largest public repository for genomic sequencing data and can be accessed for research through various cloud providers and servers from around the world.

The specific data mining software application I want to highlight today is called sratoolkit which is set of command line tools used provided by the National Center for Biotechnology Information (NCBI) along with the National Institutes of Health (NIH) to programmatically access and transfer large sequencing files. This can be done through various operating systems like Windows,  Linux or macOS but I will be focusing on the macOS workflow for this presentation.

In order to access open-data files for later downstream processing, the paths to the SRA repositories as well as the SRA IDs or SRA numbers, as they are sometimes called, that you wish to extract must be identified. The metadata regarding data attributes (i.e. single-end or paired-end files) and also database capabilities or access permissions have to be inspected before accessing and transferring so there is no data corruption or loss or other potential data issues from mistakenly using an incorrect application or function, etc. for the type of data or structure.

To select an appropriate destination for the files, we could copy and transfer the data to a cloud repository where we plan to work with it, this approach is also very accessible if working on it collaboratively. Another approach could be to utilize local storage if you have the storage and compute means and plan to work with it mostly on your own machine and easy distributed access isn’t a priority.


In our case we will be doing the latter and using Linux-based (zsh) with local storage on my machine since the number of files will be relatively small and I will remove them later anyway but If I had many large files and wanted to grant quick team access I would use a cloud repo like GitHub, AWS or ideally the UA HPC cluster (which has compute resources too not just storage) for data storage and further processing.

The first thing we want to do at this step is make sure we have the sratoolkit package for Mac installed on our local machine using the terminal or command line interface (CLI) which is also where we will be running the commands for this data mining application workflow. 

I used a package manager called Homebrew to install the package on my machine, there are others out there as well. Once you have the terminal open and verify the sratoolkit package is installed else, install it. We can now configure the application to our desired settings and after that we can look at the main functions and the arguments for them and how they could be applied in practice.

I briefly configured sratoolkit so that remote access is activated which should be the default setting and I also set the path to my local directory where I want the SRA files to be written automatically regardless of what project directory I happen to be in, otherwise the SRA files are written in the current working directory when you call the functions. Once we have that done we can now use the ‘fastq-dump’ or ‘prefetch’ commands to copy the files from the SRA to our destination location. Apparently the ‘prefetch’ command is recommended for larger datasets but since we are only going to access relatively few files from the repo we will use the former approach. And since the data we are looking to extract is paired-end data as indicated by the metadata we will use the specific syntax required, which splits the SRA data into the appropriate formatted file structure and file type (fastq).

Now that the sequencing files have been copied we can verify them by going to the specified local data directory and see if they are there. Now that we have the data locally we can begin the next steps like pre-processing and quality control before potentially implementing the newly gotten data into our current project dataset or analyses. 

Here we can see how this application of data mining is relevant to real-world research in genomics but also how it might be applied to other fields, who all have their own domain-specific version of the SRA repository and similar software applications to access and transfer data to a destination.
