MODIFIED Version of ITSx
========================

NCBI is NOT the original author of ITSx, and in almost all cases, you should ignore this repository
and go to http://microbiology.se/software/itsx

This GitHub repository holds ITSx with the addition of a little bit of error handling.  NCBI is
required to publish these changes because of ITSx's open source license.  This repo may lag behind
official releases.

NCBI is not able to provide support for ITSx.  Please contact the original authors at the URL above.

ITSx -- Identifies ITS sequences and extracts the ITS region
============================================================

Source code available at:
http://microbiology.se/software/itsx

Version: 1.1.3
ITSx -- Identifies ITS sequences and extracts the ITS region
Copyright (C) 2012-2021 Johan Bengtsson-Palme et al.
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

Bug fixes and new features in this version (1.1):
- ITSx now utilizes hmmsearch instead of hmmscan often resulting in a performance increase
- In addition, ITSx now distributes the CPU cores among processes in a more efficient manner
  Thanks to Christian Wurzbacher for helping me brainstorm this solution!
- Added the --require_anchor option causing only sequences where the complete anchor is found to be included in the output sequence
- Added the possibility for partial sequence output for the SSU, LSU and 5.8S regions (previously this was only possible for the two ITS regions)
- The HMM profile format for ITSx has been updated to HMMER3/f, and thus requires HMMER version 3.1 or later
- Added additional HMM-profiles for the ITS region a range of recently identified fungal taxa (fungi, H.hmm).
  Thanks to Leho Tedersoo, Henrik Nilsson and others who have been working on these profiles!
- Added additional HMM-profiles for the SSU end of the ITS region in Chlorophyta (algae, G.hmm).
  Thanks to Matthew Nelsen for the kind contribution!
- Changed behaviour when ITSx is called without input file specified, and added the --stdin option
- Improved handling of instances where HMMER searches are interupted
  Thanks to Bernd W for suggesting this!

Fixed bugs in this version (1.1.1):
- Fixed a bug causing the program to not accept the --truncate option

Fixed bugs in this version (1.1.2):
- Fixed a bug in which a lingering no-detections file from a previous run could cause unexpected results in the new no-detections file
- Fixed a bug causing 'G' not to be an acceptable option for profile sets (while 'green algae' was accepted, and those profiles where included in searches using all profiles)

New features in this version (1.1.3):
- Added the possibility to put the temporary directory in a custom location using the --temp option
- The software now warns when the input file contains sequences with identical identifiers

Fixed bugs in this version (1.1.3):
- Improved the handling of large input files for better tuning of scores and E-values
- Fixed a bug that returned empty sequences in the FASTA no detections file for large input files

If you encounter a bug or some other strange behaviour, please report it to:
johan[at]microbiology.se

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program, in a file called 'license.txt'. If not, see: http://www.gnu.org/licenses/.
