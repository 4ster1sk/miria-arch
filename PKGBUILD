# Maintainer: 4sterisk <4sterisk at ymail dot n e dot  j p>
pkgname=miria
pkgver=2.0.2+117
pkgrel=1
pkgdesc="Miria is Misskey Client App for iOS, Android and many targets which made by Flutter."
arch=('x86_64')
url="https://shiosyakeyakini.info/miria_web/"
license=('AGPL3')
depends=('gtk3' 'mpv' 'libsecret')
makedepends=('fvm' 'cmake' 'ninja' 'clang' 'nasm' 'llvm-libs')
source=("https://github.com/shiosyakeyakini-info/$pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('060868851bad50018fb4094d61535d297b55ed83c8133e7972f9f3e60ea7f901')

build() {
    cd "$pkgname-${pkgver//+/-}"
    export PUB_CACHE="./pub-cache"
    fvm install --setup
    fvm flutter pub get
    # fix compile error
    sed -i 's/operator ""\s\+_json/operator ""_json/g' \
        ./linux/flutter/ephemeral/.plugin_symlinks/flutter_secure_storage_linux/linux/include/json.hpp

    fvm flutter build linux --release
}

package() {
    cd "$pkgname-${pkgver//+/-}"
    mkdir -p \
        "${pkgdir}/opt/miria" \
        "${pkgdir}/usr/share/applications" \
        "${pkgdir}/usr/share/pixmaps" \
        "${pkgdir}/usr/share/licenses/$pkgname" \
        "${pkgdir}/usr/bin"
    
    cp -rp ./build/linux/x64/release/bundle/* "${pkgdir}/opt/miria/"
    cp ./snap/gui/miria.desktop "${pkgdir}/usr/share/applications/miria.desktop"
    cp ./assets/images/icon.png "${pkgdir}/usr/share/pixmaps/miria.png"
    cp ./LICENSE "${pkgdir}/usr/share/licenses/$pkgname/LICENSE"
    ln -s /opt/miria/miria "${pkgdir}/usr/bin/miria"
    sed -i -E 's|^Version=.*|Version=1.5|g' "${pkgdir}/usr/share/applications/miria.desktop"
    sed -i -E 's|^Icon=.*|Icon=miria|g' "${pkgdir}/usr/share/applications/miria.desktop"
}