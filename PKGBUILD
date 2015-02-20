pkgname=performous
pkgver=1.0
pkgrel=2
pkgdesc='A free game like "Singstar", "Rockband" or "Stepmania"'
arch=( 'x86_64')
url="http://performous.org/"
license=('GPL')
depends=('boost-libs' 'glew' 'libxml++' 'portaudio-svn' 'portmidi' 'librsvg' 'ffmpeg' 'opencv' 'sdl2')
makedepends=('cmake' 'pkgconfig' 'help2man' 'boost' 'mesa')
optdepends=('performous-freesongs: free songs for performous')
source=(https://github.com/performous/${pkgname}/archive/${pkgver}.tar.gz)
md5sums=('cbeec2f0c0114cc499746c1e33f56055')

build() {
  cd performous-${pkgver}

  mkdir -p build
  cd build

  cmake -DCMAKE_BUILD_TYPE=Release \
	-DCMAKE_INSTALL_PREFIX=/usr ..

  make
}

package() {
  cd performous-${pkgver}/build

  make DESTDIR="$pkgdir" install
}
