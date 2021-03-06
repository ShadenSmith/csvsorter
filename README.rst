==========
CSV Sorter
==========

Fork of the csvsort_ for Python 3.
For sorting CSV files on disk that do not fit into memory. The merge sort algorithm is used to break up the original file into smaller chunks, sort these in memory, and then merge these sorted files.

.. _csvsort: https://bitbucket.org/richardpenman/csvsort

=============
Example usage
=============

.. sourcecode:: python

    >>> from csvsorter import csvsort
    >>> # sort this CSV on the 5th and 3rd columns (columns are 0 indexed)
    >>> csvsort('test1.csv', [4,2])  
    >>> # sort this CSV with no header on 4th column and save results to separate file
    >>> csvsort('test2.csv', [3], output_filename='test3.csv', has_header=False)  
    >>> # sort this TSV on the first column and use a maximum of 10MB per split
    >>> csvsort('test3.tsv', [0], max_size=10, delimiter='\t')  
    >>> # sort this CSV on the first column, force quotes around every field (default is csv.QUOTE_MINIMAL) and use windows-1250 encoding
    >>> import csv
    >>> csvsort('test4.csv', [0], quoting=csv.QUOTE_ALL, encoding='windows-1250')

..


=======
Install
=======

.. sourcecode:: bash

    $ pip install csvsorter

..
