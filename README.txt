=============================================================
Samba 3.6.25 for Tru64 UNIX (OSF/1 5.1b) - Binary Package
Target: alphaev56-dec-osf5.1b
=============================================================

1. DESCRIPTION
   This package contains Samba 3.6.25 built natively on
   Tru64 UNIX v5.1B (DEC Alpha EV56).
   It includes runtime shared libraries:
     - GNU libiconv (libiconv.so)
     - zlib (libz.so.1.2.8)

2. EXTRACT & FIX SYMLINKS
   Run the following commands as root to extract:

   # cd /usr/local
   # gzip -dc /path/to/Tru64_Samba_3.6.25_with_libs.tar.gz | /sbin/tar xvf -

   # Verify/fix library symlinks in /usr/local/lib:
   # cd /usr/local/lib
   # ln -sf libiconv.so.3.1.0 libiconv.so
   # ln -sf libiconv.so.3.1.0 libiconv.so.3
   # ln -sf libz.so.1.2.8 libz.so.1
   # ln -sf libz.so.1.2.8 libz.so

3. ENVIRONMENT SETUP (.profile)
   Ensure /usr/local/lib and Samba paths are in your environment:

   export PATH=/usr/local/samba/sbin:/usr/local/samba/bin:$PATH
   export LD_LIBRARY_PATH=/usr/local/lib:/usr/shlib:$LD_LIBRARY_PATH

4. VERIFICATION
   Test the installation using:

   # /usr/local/samba/sbin/smbd -V
   # /usr/local/samba/bin/testparm -V
=============================================================
