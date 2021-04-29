#  Transferring data from Pleiades
#til/Pleiades

Moving files from the NASA Ames Pleiades supercomputer can be a challenge for two reasons: the size of your data files and the tools available to copy files from Pleiades to a local machine.  The second problem can be addressed using Pleiades `shiftc` software.  My data transfer workflow is based on the instructions  for shiftc from the NASA High-End Computing Capability (HECC): [Using Shift for Remote Transfers and Tar Operations - HECC Knowledge Base](https://www.nas.nasa.gov/hecc/support/kb/using-shift-for-remote-transfers-and-tar-operations_514.html))

Here are my steps for transferring data from Pleiades:
1. Tar the directory using mtar on Pleiades. mtar uses the same syntax as tar.
2. From my own machine, use the command `sup shiftc ` followed by the usual syntax for `shiftc` .

I need to tar the directories first. A recursive `shiftc` doesn’t work because `shiftc` follows symlinks. I definitely don’t want to follow symlinks. The Data files in the code are huge.

**Note:** These instructions only work for people with approved access to the NASA HECC resources.
