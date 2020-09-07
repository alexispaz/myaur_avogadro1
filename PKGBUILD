# Maintainer: Federico Vivaldi <f.vivaldi1@gmail.com>

pkgname="avogadro-git-eigen3"
pkgver=1.2
pkgrel=1
pkgdesc='Molecule editor and visualizer designed for cross-platform use'
arch=("x86_64")
url="http://avogadro.cc/"
license=('GPL2')
depends=('eigen' 'openbabel2' 'qt4')
makedepends=('cmake' 'doxygen' 'git')
source=("${pkgname}"::'git+https://github.com/Avogadro/avogadro.git')
provides=('avogadro')

build() {
        cd "$pkgname"
        
	if [ -e $pkgname/build]
	then
		cd build
	else
		mkdir build
        	cd build
    	fi
        cmake -DOPENBABEL2_LIBRARIES=/usr/lib64/libopenbabel.so.5 ../
        make -j2
}


package() {
	cd "$pkgname/build"
        make DESTDIR="$pkgdir/" install
        mv $pkgdir/usr/local/share/man $pkgdir/usr/local/man
}



md5sums=('SKIP')
