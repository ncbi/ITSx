ITSx -- Identifies ITS sequences and extracts the ITS region

Source code available at:
http://microbiology.se/software/itsx

Version: 1.0.11
ITSx -- Identifies ITS sequences and extracts the ITS region
Copyright (C) 2012-2014 Johan Bengtsson-Palme et al.
Contact: Johan Bengtsson-Palme, johan[at]microbiology.se
Programmer: Johan Bengtsson-Palme

Full installation instructions can be found in the User's Guide.
A quick installation guide follows below.

ITSx requires Perl and HMMER3.

1) Perl is usually installed on Unix-like systems by default. If not, it can be retrieved from http://www.perl.org/

2) HMMER3 can be found at http://hmmer.janelia.org/software
Download it and follow the on site instructions for installation.

3) Obtain the ITSx package from http://microbiology.se/software/itsx
Unpack the tarball and move into the newly created "ITSx" directory.

4) Copy the ITSx file and the ITSx_db directory to your preferred bin directory.

5) To test if ITSx was successfully installed type "ITSx --help" on the command-line. You should now see the ITSx help message.


To run ITSx, you need a FASTA-formatted output file. You can e.g. use the test.fasta file supplied with the package. To check for ITS sequences in the test file, type "ITSx -i test.fasta -o test" on the command line. If you are on a multicore machine, you might want to use the "--cpu 2" option to speed up the processes by using two (or more) cores.

Bug fixes in this version:
- Fixed an output bug related to the use of the --partial option

If you encounter a bug or some other strange behaviour, please report it to:
johan[at]microbiology.se

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program, in a file called 'license.txt'. If not, see: http://www.gnu.org/licenses/.
