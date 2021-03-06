phraug
======

A set of simple Python scripts for pre-processing large files, things like splitting and format conversion. The names _phraug_ comes from a great book, _Made to Stick_, by Chip and Dan Heath.

See [http://fastml.com/processing-large-files-line-by-line/](http://fastml.com/processing-large-files-line-by-line/) for the basic idea.

There's always at least one input file and usually one or more output files. An input file always stays unchanged.

Format conversion
-----------------

`csv2libsvm.py <input file> <output file> [<label index = 0>] [<skip headers = 0>]`

Convert CSV to LIBSVM format. If there are no labels in the input file, specify _label index_ = -1. If there are headers in the input file, specify _skip headers_ = 1.


`csv2vw.py <input file> <output file> [<label index = 0>] [<skip headers = 0>]`

Convert CSV to VW format. Arguments as above.


`libsvm2csv.py <input file> <output file> <input file dimensionality>`

Convert LIBSVM to CSV. You need to specify dimensionality, that is a number of columns (not counting a label).


`libsvm2vw.py <input file> <output file>`

Convert LIBSVM to VW.


`tsv2csv.py <input file> <output file>`

Convert tab-separated file to comma-separated file.

Other operations
----------------

`chunk.py <input file> <number of output files> [<random seed>]`

Split a file randomly line by line into a number of smaller files. Might be useful for preparing cross-validation. Output files will have the base nume suffixed with a chunk number, for example `data.csv` will be chunked into `data_0.csv`, `data_1.csv` etc.

`count.py <input file>`

Count lines in a file. On Unix you can do it with `wc -l`

`sample.py <input file> <output file> [<P = 0.5>]`

Sample lines from an input file with probability P. Similiar to `split.py`, but there's only one output file. Useful for sampling large datasets.


`split.py <input file> <output file 1> <output file 2> [<P = 0.9>] [<random seed>]`

Split a file into two randomly. Default P (probability of writing to the first file) is 0.9. You can specify any string as a seed for random number generator.


`subset.py <input file> <output file> [<offset = 0>] [<lines = 100>]`

Save a subset of lines from an input file to an output file. Start at _offset_ (default 0), save _lines_ (default 100).
	
	


