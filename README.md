# Tutorial BLAST Nextflow
Exercise for *Nextflow* learning that allow to BLAST 5 short sequences against a database created from a genome. 

Reference: [Exercise](https://bioinformaticsworkbook.org/dataAnalysis/nextflow/02_creatingAworkflow.html#gsc.tab=0)

## Git setting
1. Create a new repository in the profile
2. Clone it locally by using: git clone git@github.com:isugifNF/tutorial.git
3. Create two files: nextflow.config and main.nf in the terminal (touch command)

The created files and all the subseqeunt modifications are done locally. to be shown in the remote repository they must be added and committed. This can be done by:
- `git add <files>` 
- `git commit -m <comment>` 
- `git push`

This must be done each time the modified file is wanted to be uploaded in the repository.

## BLAST script
The script is composed by the definition of a **help message** that, if present allows to explain what the script does and what arguments are required. 

Its definition is followed by an **if** statement that allows its printing if the help parameter is present. 

The next step is the check for the presence of a **genome** provided as argument. If present, `mkblastdb`is run to create a database to which the program can blast the sequences, other wise it uses the default parameters. 

In the end, the fasta file with the **query** sequences is split in chuncks and passed to the *runBlast* process, which allows to run the blast software. 

## Config file
The *nextflow.config* file is used to set all the default parameters that are used by the script for the execution. The directives set are: 
- params: default values for all variables taken as input
- timeline: analysis of the run
- report: analysis of the run
- executor: setting of the executor and its options
- profile: choice of the executor
