# Ungoogled Chromium Void Linux
Void Linux repository for Ungoogled Chromium fork.

<H1>How to install</H1>

Please note that this process was only tested on x86_64-glibc, which is the main focus of this repository. Feel free to tell me if this works well on i86 and ARM (GlibC). I'll consider to add a Musl package also.

 <H2>Building from template</H2>

First of all, we'll need <code>xtools</code> installed in order to use <code>properly</code> xbps-src:

     sudo xbps-install xtools

If you haven't cloned the <code>void-packages</code> repository already, do it now:

     git clone --depth=1 https://github.com/void-linux/void-packages

Prepare the build environment (do this once if not done already):

     cd void-packages
     ./xbps-src binary-bootstrap
     
 <H3>Packaging to XBPS via pre-built binary tarball (recommended)</H3>

This template uses the <a href=https://github.com/mdedonno1337>Marco De Donno's</a> pre-built portable tarball repository, and packages it to XBPS format. This is recommendable if your machine does not have the requirements to compile the entire package or if you don't have the time to do it. This is the only functional method for now.

Clone the template to <code>void-packages</code> directory, copy the template, build it and install:

     git clone https://github.com/KF-Art/ungoogled-chromium-void/ && cd ungoogled-chromium-void
     cp -r ungoogled-chromium-bin ../srcpkgs/ && cd ..
     ./xbps-src pkg ungoogled-chromium-bin # compile the package
     xi ungoogled-chromium-bin # install the package
     
  <H3>Building from source code (Experimental and not tested)</H3>

This method is purely experimental, has not undergone sufficient testing, and does NOT work at the moment. This section is reserved for testing and polishing the code until it is compiled correctly. Proceed with care.

     # Clone this repo, if not done yet.
     git clone https://github.com/KF-Art/ungoogled-chromium-void/ && cd ungoogled-chromium-void
     cp -r ungoogled-chromium ../srcpkgs/ && cd ..
     ./xbps-src pkg ungoogled-chromium # compile the package.
     xi ungoogled-chromium # install the package.

  
 <H2>[WIP] Installing pre-built XBPS binary (x86_64-glibc only)</H2>
There is also an binary package to install directly to your system. I recommend this if you don't want to go through the building process, but this may be outdated sometimes. I'll try to mantain this updated as is possible for me.

To install it, just do the following steps:

     git clone https://github.com/KF-Art/ungoogled-chromium-void
     cd ungoogled-chromium-void/bin/ 
     xbps-rindex -a *.xbps
     sudo xbps-install --repository=$PWD ungoogled-chromium-bin

I'll consider try to create my own repository to provide updates faster.
     
<H3>Updating cloned repository contents</H3>

     cd /path/to/ungoogled-chromium-void
     git pull
