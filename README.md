############################################################################
###     BandUP: Band Unfolding code for Plane-wave based calculations             
############################################################################
###### Copyright (C) 2013-2017 Paulo V. C. Medeiros - pvm20@cam.ac.uk
##### Please visit http://www.ifm.liu.se/theomod/compphys/band-unfolding

BandUP is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

BandUP is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with BandUP.  If not, see <http://www.gnu.org/licenses/>.

<!-- ============================================================================= -->
#### Plane-wave codes currently supported by BandUP
--------------------------------------------------------------------------------------
    * At the moment, BandUP can parse wavefunctions generated by: 
        * VASP
        * Quantum ESPRESSO
        * ABINIT
        * CASTEP
    * Feel free to contact me if you use another plane-wave code and would like to have 
      support to it added in BandUP
        * As usual, I'll do my best to help you out.
        * Of course, you can also collaborate by writing/sending me a routine to read 
          the wavefunctions produced by your code. If you already have a routine, then
          we'd only need to write an interface to it :)

<!-- ============================================================================= -->
#### How to compile BandUP
--------------------------------------------------------------------------------------
    * Run the "build.sh" script: ./build.sh
    * A directory named "BandUP_bin" will be created.
        * You'll find the executables for BandUP in it.
        * NB: As of May 2017, you should use the executable "bandup". This is a Python
              interface for all BandUP functionalities (getting SC-Kpoints pre-unfolding,
              the main unfolding code, as well as the plotting tool).
    * This should work in most Unix environments with up-to-date Intel or GNU compilers 
      installed. 
        * Do check, however, the system requirements below if you have any problem.

<!-- ============================================================================= -->
#### System requirements:
--------------------------------------------------------------------------------------
    * Preferably Linux
        * Might work in other environments based on Unix
    * Fortran 95 and C compilers
        * Preferably Intel compilers (ifort and icc), version 12.1.4 (or higher)
        * Should also work with GNU compilers (gfortran and gcc), version 5.2 (or higher)
    * Python 2.X (X>=7) for the post-processing utilities
        * You will need to have the following packages installed 
          (you probably already have most of them; try running the code before worrying):
            * argparse
            * numpy 
            * scipy
            * matplotlib
            * os
            * sys
            * subprocess
            * fractions
            * json
            * shutil
            * collections
        * Please let me know if I've forgotten to list any other package!
    * Optional: Either PyQt4 or PyQt5
            * This is needed only if you want to use the graphical user interface 
              (GUI) version of the plotting tool.
            * If the GUI doesn't work with you, you can keep using the plotting tool 
              in the command line, just as usual.
            
<!-- ============================================================================= -->
#### Publications:
--------------------------------------------------------------------------------------
    * If you use BandUP (or any part or modified version of it) in your work, you should:
          * State EXPLICITLY that you've used the BandUP code (or a modified version of it).
          * Read and cite the following papers (and the appropriate references therein):

            >>> Phys. Rev. B 89, 041407(R) (2014) <http://dx.doi.org/10.1103/PhysRevB.89.041407>

            >>> Phys. Rev. B 91, 041116(R) (2015) <http://dx.doi.org/10.1103/PhysRevB.91.041116>

      * An appropriate way of acknowledging the use of BandUP in your publications would be, 
        for instance, adding a sentence like 
                "The unfolding has been performed using the BandUP code",
        followed by the citation to our papers.

<!-- ============================================================================= -->
#### IMPORTANT: Major changes in V3.0.0:
--------------------------------------------------------------------------------------
    * As of May 2017, you should use the executable "bandup" for all BandUP tasks
      This contains a Python iterface to the Fortran codes "get_SCKPTS_pre_BandUP.x" and
      "BandUP.x" that used to be executed directly in previous versions of BandUP. It 
      also contains a plotting task that reimplements the previously available 
      "plot_unfolded_EBS_BandUP.py" script and its GUI, which no longer exist as 
      individual scripts since V3.0.0.

<!-- ============================================================================= -->
#### Tips:
--------------------------------------------------------------------------------------
    * BandUP accepts some *optional command line arguments and flags*. To find out more
      about them, run the code with the *flag '-h'*.
    * Since BandUP's plotting task has a lot of different options, I've given it a GUI.
      You can launch it by executing BandUP with the options "plot --gui"
      * This requires that you have either PyQt4 or PyQt5 in your python install. If
        the GUI doesn't work for you, you can still do the plots using the command line
    * It might be handy placing a symlink to the "bandup" executable in some directory 
      in your PATH, or, less preferably, including the whole BandUP_bin in your PATH. 
      By doing so, you'll be able to use BandUP in whataver directory you're working at.


<!-- ============================================================================= -->
#### Please mind that:
--------------------------------------------------------------------------------------
    * Although we have very limited time and resources, we do our best to provide good
      user support. To help us to continue to do so, however, please make sure to do 
      the following before writing to us to request assistance:
        * Cerify that all system requirements are fulfilled
        * Certify that you are using the latest version of BandUP
        * *Run BandUP with the option "-h"* to get a list of all supported options.
          Most of the times, the information you need is already available in the help
          messages displayed!
    * Although I've tried to make the compilation as simple as possible - and it has 
      indeed worked fine so far with many combinations of compilers, computers, and 
      operating systems, I cannot guarantee that it will always work smoothly. 
      You might eventually need to play a bit with the scripts and, very rarely, 
      with the Makefiles and source code.
    * In the calculations and tests I've performed with BandUP so far, I've mostly 
      used intel compilers (v. 12.1.4) and, a few times, GNU compilers (v. 5.2). 
      I *believe* that you should have no problems using other versions of ifort/icc 
      (and *maybe* even other non-intel compilers), as well as more recent versions 
      of gfortran/gcc. Mind, however, that I cannot guarantee that it will work in 
      100% of the cases.
    * Last, but not least: Always check the results with a critical eye, specially 
      if they don't look the way you think they are supposed to. Please notify me if 
      weird stuff happens and you think it's the code's fault (but do double-check first)!
 

Have fun! 
Let us know if you have problems! 
