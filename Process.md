# RVisualization
Goal is to create a visualization tool in R for genomic data

Researchers often collect genomic data in massive groups due to the repetitive nature
of DNA sequencing, making it hard to find and analyze specific values. Our goal is to solve
this problem by creating a visualization tool that locates and visualizes these values
with the rest of the data on the go. 

We started off by using the data from one sample. Our first idea was to generate
a PNG file for every gene in the sample. But the sample file contained data for
20,000+ genes so the program had to open and close 20,000 different PNG files which took
it over 20 hours to do. This idea was thus not feasible. We then decided to use
a PDF file with each page of the PDF corresponding to a different gene so that
the program would only have to open and close one file as opposed to 20,000.
After implementing this change, the program only took 90 seconds to complete
for one sample. However, at the time we were only generating simple scatter plots
since our dataset only consisted of one sample, and we wanted to test this program
on a 400 sample dataset. We also wanted to change the program so that a boxplot
encompassing data from all 400 samples would be generated for each gene in the dataset. 
20,000+ box plots would thus be generated and then these boxplots would be placed in a
PDF file that would be copied so that 400 of the same pdf file would exist, one for
each sample in the dataset. We would then add scatter overlays to each box plot in every file 
that would come from the specific sample the pdf corresponded to. However, this
idea proved to not be feasible because the pdfs could not be edited once they were
closed. So we decided to make a dynamic on the go web app using the shiny package
that would visualize data as the user requested. The user would upload a table of data
which would then be read in. Then the user would select a gene and a specific sample
to see a visualized version of the data for that particular gene. 
