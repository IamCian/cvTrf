# cv.tmac

`Troff`/`Groff` macros for creating CV PDF documents.

## Includes

- header 
- section headings
- columned lists
- timelines/dates
- (documentation in file!)

## Invocation 

These macros cab be used with groff, simply by specifying through flag
arguments, the directory they are located, with `-M`, and their name (without
the extension) with `-m`, as in:

	$ groff -Tpdf -M . -m cv myFile.trf > myFile.pdf

to specify the file `cv.tmac`, which is in the current directory and we want to
use it. Or, if installed (see below), we can simply run:
	
	$ groff -Tpdf -m cv myFile.trf > myFile.pdf

## Installation

A more permanent solution is to install them to a local `Troff`/`Groff` macro
directory, `~/.local/share/troff/tmac/`, which involves setting the `Groff`
environment variable `GROFF_TMAC_PATH`.

	$ cd
	$ mkdir -p .local/share/troff/tmac
	$ git clone https://git.cianb.xyz/cvTrf
	$ cp cvTrf/cv.tmac .local/share/troff/tmac/
	$ echo export GROFF_TMAC_PATH="${HOME}/.local/share/troff/tmac/" >> .profile
	$ source .profile
	$ rm -rf TrfCv
