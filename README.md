# dropbox_linux_x86_64_glibc2.4_buildout
A zc.buildout that installs the Dropbox daemon and glibc-2.4 on a Linux x86_64 system without glibc-2.4 (e.g.: DreamHost VPS)

By Marc Abramowitz [http://marc-abramowitz.com](http://marc-abramowitz.com)

This is an attempt to make repeatable [the process that I followed to install Dropbox on my DreamHost VPS](http://marc-abramowitz.com/archives/2011/04/19/running-dropbox-on-dreamhost/). This was tricky because the Dropbox software is closed-source and it contains binaries compiled against glibc 2.4, whereas my VPS server is using glibc 2.3. This buildout downloads and compiles glibc 2.4 and installs it in a sandbox with the Dropbox software. It also sets up Supervisor and uses it to manage the Dropbox daemon.

## Installation

<pre>
$ export TMPDIR=$(pwd)/tmp; mkdir ${TMPDIR}; python bootstrap.py && bin/buildout
</pre>
