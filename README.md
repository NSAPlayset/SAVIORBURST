SAVIORBURST

A tool for building SVF files from OpenOCD logs.

----------

Before building OpenOCD, the following patches need to be applied to OpenOCD 0.9.0 
in order to support SVF generation: jtag-verbose.patch and ftdi-jtag-printing.patch 
(if using an FTDI based JTAG adapter).

Additionally, to prevent data from being truncated in the log file, the maximum 
length of scan chain data to be logged may need to be increased. This can be 
accomplished by running:

sed -i 's/define DEBUG_JTAG_IOZ 64/define DEBUG_JTAG_IOZ 1024/' src/jtag/jtag.h

----------

OpenOCD must be configured with verbose JTAG logging enabled. FTDI support (if 
needed) must also be explicitly enabled.

./configure --enable-verbose-jtag-io [--enable-ftdi]

----------

Once an OpenOCD log file has been created, log2svf.py can be used to convert it to
an SVF file.

----------

Mouser Cart (Untested) for SOLDERPEEK parts can be found here:

http://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=5cc594b9ce