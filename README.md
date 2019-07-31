# Freetype-library-compilation-on-Fedora29

# Insalling required tools

dnf install glibc.i686 zlib.i686 bzip2-libs.i686 libXft.i686 libXext.i686 ncurses-compat-libs.i686 

yum install libstdc++-devel.i686 glibc-devel.i686 gcc gcc-c++ freetype-devel glib2-devel cairo-devel

# Now you can quite happily compile your executable with the -m32 flag, as below:


Extract freetype folder

-    tar -xjvf freetype-2.4.12.tar.bz2
-    cd freetype-2.4.12/
-    ./configure --build=i686-pc-linux-gnu "CFLAGS=-m32" "CXXFLAGS=-m32" "LDFLAGS=-m32"
-    make -j8

# Now copy compiled files to {{modelsim_ase/lib32}} folder

-    cp objs/.libs/libfreetype.* /home/user/altera/13.1/modelsim_ase/lib32/


# For modelsim, Dont need to touch harfbuzz unless an issue persist!!!

#  Harfbuzz needs to be installed after compilation


Extract harfbuzz

-    tar -xzf harfbuzz-2.5.3.tar.xz
-    cd harfbuzz-2.5.3/
-    ../configure --prefix=/usr --with-gobject --with-graphite2 && make
-    make install









