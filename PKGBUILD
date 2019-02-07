# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-game-libretro-scummvm
pkgver=2.0.0.3
_codename=Leia
pkgrel=1
pkgdesc="Libretro wrapper for Kodi's Game API"
arch=('x86_64')
url='https://github.com/kodi-game/game.libretro.scummvm'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-game')
depends=('kodi-addon-game-libretro' 'libretro-scummvm')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/kodi-game/game.libretro.scummvm/archive/$pkgver-$_codename.tar.gz")
sha512sums=('a771fb283ce4fa71a15fa4269407867678b9921d65e212280cee2281fff46417daa03d5360af28078cff446ced2fea5e29c87b0d63ecf7c62b8b1ed1de657c2d')

build() {
    cd "game.libretro.scummvm-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "game.libretro.scummvm-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

