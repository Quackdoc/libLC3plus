#Maintainer : Mitchel Stewart <quackdoctech@gmaiil.com>

pkgname=liblc3plus-float
pkgver=1.3.6
pkgrel=1
pkgdesc='Shared LC3 float library'
arch=('x86_64')
url='https://www.iis.fraunhofer.de/en/ff/amm/communication/lc3.html'
license=('custom')
depends=(
cmake
)
makedepends=(
  clang
  git
)
provides=('libLC3plus.so')
source=('https://www.etsi.org/deliver/etsi_ts/103600_103699/103634/01.03.01_60/ts_103634v010301p0.zip'
        'CMakeLists.txt'
        'LC3plus.pc.in')

sha256sums=('bb0a15b4447c3fae070f8810ba0991cc983deb3ce94a9f55cd37e1052ccef56e'
            '42c0465499568b862f6f1729f9fe12f9505f357c682ef6f25c99dfa7f3b2353c'
            '69066e5f5d4a44cfac50b20d03b270a61d5eb9b3226aa198fe716ebf61a0de75')

build() {
    cd $srcdir/ETSI_Release/LC3plus_ETSI_src_v172062927c2_20210930/src/floating_point/
    cp $srcdir/CMakeLists.txt ./
    cp $srcdir/LC3plus.pc.in ./
    mkdir -p build && cd build
    cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr ..
    make
}

package() {
  cd $srcdir/ETSI_Release/LC3plus_ETSI_src_v172062927c2_20210930/src/floating_point/build
  make DESTDIR="$pkgdir/" install
}
