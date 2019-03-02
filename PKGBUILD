pkgname=lightrss
pkgver=0.1
pkgrel=1
pkgdesc="A simple qt based rss feed reader"
url="https://github.com/deussomniat/${pkgname}"
license=('GPL')
arch=('x86_64')
depends=('qt5-base')
makedepends=('make')
source=(
    "${url}/archive/v${pkgver}.tar.gz"
    'lightrss.desktop'
)
sha256sums=(
    '3d88d97d064c0c8256de779bb5be8f02e82d46ff38f51eed1262c62ce0e610af'
    '48922e5c467ca65c1b6cbdbe84782f2256852ed0db72307ca946febcee97ecca'
)

prepare() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    /usr/lib/qt5/bin/qmake
}

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    install -Dm755 "${srcdir}/${pkgname}-${pkgver}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
    install -Dm755 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
    install -Dm755 "${srcdir}/${pkgname}-${pkgver}/images/rss48.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/${pkgname}.png"
}
