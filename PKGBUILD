# Maintainer: 4sterisk <146138447+4ster1sk@users.noreply.github.com>
pkgname=miria
pkgver=2.0.0+110
pkgrel=1
pkgdesc="Miria is Misskey Client App for iOS, Android and many targets which made by Flutter."
arch=('x86_64')
url="https://shiosyakeyakini.info/miria_web/"
license=('AGPL3')
depends=('gtk3' 'mpv' 'libsecret')
source=("https://github.com/4ster1sk/miria/releases/download/v2.0.0%2B110/miria_2.0.0+110_amd64.deb")
sha256sums=('SKIP')

package() {
    bsdtar -xf "${srcdir}/${pkgname}_${pkgver}_amd64.deb" -C "${srcdir}"
    bsdtar -xf "${srcdir}/data.tar.gz" -C "${pkgdir}"
}
