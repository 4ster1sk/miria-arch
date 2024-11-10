# Maintainer: 4sterisk <146138447+4ster1sk@users.noreply.github.com>
pkgname=miria
pkgver=2.0.1+115
pkgrel=1
pkgdesc="Miria is Misskey Client App for iOS, Android and many targets which made by Flutter."
arch=('x86_64')
url="https://shiosyakeyakini.info/miria_web/"
license=('AGPL3')
depends=('gtk3' 'mpv' 'libsecret')
source=("https://github.com/shiosyakeyakini-info/miria/releases/download/v2.0.1+115/miria_2.0.1+115_amd64.deb")
sha256sums=("19a6230e7730fa7c8fe7b175e0ffb03871f62c8b98b4b1da2c634392b2abf4aa")

package() {
    bsdtar -xf "${srcdir}/${pkgname}_${pkgver}_amd64.deb" -C "${srcdir}"
    bsdtar -xf "${srcdir}/data.tar.gz" -C "${pkgdir}"
}
