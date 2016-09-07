# runSTRUCTURE

This program is a small BASH wrapper script to automate [STRUCTURE](http://pritchardlab.stanford.edu/structure.html) across any number of K, with multiple iterations per K on a SGE cluster

## Download 

    git clone https://github.com/m-richardson/runSTRUCTURE

## Disclamer 

This program works well for a specific type of data; it has been built to work on the SGE cluster at Deakin University. You may have to change certain lines of code to get it to work on your cluster. It will work on a single machine if you uncomment the code at the bottom of the script - please remember to comment out the first nested while loops. You will need to produce the mainparams and extraparmas files required by [STRUCTURE](http://pritchardlab.stanford.edu/structure.html) and edit them according to your analysis requirements.

## Pre-requisite programs

[STRUCTURE](http://pritchardlab.stanford.edu/structure.html) - make sure the binary is available in your PATH


## Example usage

    runSTRUCTURE 18 10 mainparams extraparams str_output genotypes.str


## Detailed usage

    runSTRUCTURE max_K iterations mainparams_file extraparams_file output_directory input_file	
    

SPECIFY:

max_K = highest value of K to run STRUCTURE for

iterations = number of iterations per K

mainparams = the mainparams file for STRUCTURE 	

extraparams = extraparams file for STRUCTURE

output_directory = the output directory name

input_file = input STRUCTURE file


IMPORTANT:

make sure the STRUCTURE binary is in your PATH (i.e. in ~/.bash_profile). It works best when you run it from within the directory containing your mainparams, extraparams and input.str files. You dont need to do this as long as you specify the full path to those files. It will create an output directory for each K which contains the results for each of the different iterations.

Have fun and enjoy.

Mark Richardson (email m.richardson@deakin.edu.au)
