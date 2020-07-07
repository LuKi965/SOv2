Requirements for Debian-based distributions:

- Build tools: g++ make cmake
- Qt5: qtbase5-dev qtbase5-dev-tools qttools5-dev qttools5-dev-tools
- X11: xorg-dev libxtst-dev
- libjpeg: libjpeg-dev provided by libjpeg-turbo8-dev or libjpeg62-turbo-dev
- zlib: zlib1g-dev
- OpenSSL: libssl-dev
- PAM: libpam0g-dev
- procps: libprocps-dev
- LZO: liblzo2-dev
- QCA: libqca2-dev libqca-qt5-2-dev
- LDAP: libldap2-dev
- SASL: libsasl2-dev

As root you can run

	apt install g++ make cmake qtbase5-dev qtbase5-dev-tools qttools5-dev qttools5-dev-tools \
	            xorg-dev libxtst-dev libjpeg-dev zlib1g-dev libssl-dev libpam0g-dev \
	            libprocps-dev liblzo2-dev libqca2-dev libqca-qt5-2-dev libldap2-dev \
	            libsasl2-dev



Requirements for RedHat-based distributions:

- Build tools: gcc-c++ make cmake rpm-build
- Qt5: qt5-devel
- X11: libXtst-devel libXrandr-devel libXinerama-devel libXcursor-devel libXrandr-devel libXdamage-devel libXcomposite-devel libXfixes-devel
- libjpeg: libjpeg-turbo-devel
- zlib: zlib-devel
- OpenSSL: openssl-devel
- PAM: pam-devel
- procps: procps-devel
- LZO: lzo-devel
- QCA: qca-devel qca-qt5-devel
- LDAP: openldap-devel
- SASL: cyrus-sasl-devel

As root you can run

	dnf install gcc-c++ make cmake rpm-build qt5-devel libXtst-devel libXrandr-devel libXinerama-devel libXcursor-devel \
             libXrandr-devel libXdamage-devel libXcomposite-devel libXfixes-devel libjpeg-turbo-devel zlib-devel \
             openssl-devel pam-devel procps-devel lzo-devel qca-devel qca-qt5-devel openldap-devel cyrus-sasl-devel


### Configuring and building sources

Run the following commands:

	mkdir build
	cd build
	cmake ..
	make -j4

NOTE: If you want to build a .deb or .rpm package for this software, instead of the provided cmake command, you should use:

	cmake -DCMAKE_INSTALL_PREFIX=/usr ..

to install package files in /usr instead of /usr/local.

If some requirements are not fullfilled, CMake will inform you about it and
you will have to install the missing software before continuing.

You can now generate a package (.deb or .rpm depending what system you are in).

For generating a package you can run

	fakeroot make package
