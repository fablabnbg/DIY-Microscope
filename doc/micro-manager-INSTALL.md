## Linux Mint 18.1

Study 
* https://github.com/micro-manager/micro-manager/blob/master/doc/how-to-build.md <br>
* https://micro-manager.org/wiki/Linux_installation_from_source_(Ubuntu)

<pre>
apt install openjdk-9-jdk
apt install subversion build-essential autoconf automake libtool libboost-all-dev zlib1g-dev swig ant

cd ~/Downloads; wget http://wsr.imagej.net/distros/linux/ij150-linux64-java8.zip
sudo unzip ij*-linux*.zip -d /usr/local/
sudo rm -rf /usr/local/ImageJ/jre
sudo chmod a+Xr /usr/local/ImageJ


cd ~/src/github/micro-manager
git clone https://github.com/micro-manager/micro-manager.git

svn co https://valelab4.ucsf.edu/svn/3rdpartypublic
 ...
 Could not read chunk delimiter: Secure connection truncated (https://valelab4.ucsf.edu)

svn cleanup 3rdpartypublic
svn update 3rdpartypublic
 ...
 svn: E175009: Die XML-Antwort enthält ungültiges XML

svn cleanup 3rdpartypublic
svn update 3rdpartypublic

apt install libboost-all-dev zlib1g-dev
apt install libusb-dev libfreeimage-dev python-numpy-dev
apt install libcv-dev libopencv-dev libgphoto2-dev

cd micro-manager
./autogen.sh
./configure --enable-imagej-plugin=/usr/local/ImageJ

make fetchdeps

make
sudo make install
</pre>
