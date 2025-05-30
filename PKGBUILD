# Maintainer: Aaron Graves <linux@ajgraves.com>
# Contributor: Morten Linderud <morten@linderud.pw>
# Contributor: Sebastian Stenzel <sebastian.stenzel@gmail.com>
# Contributor: Julian Raufelder <arch@raufelder.com>
# Contributor: Armin Schrenk <armin.schrenk@skymatic.de>

pkgname=cryptomator-bin
pkgver=1.16.0
pkgrel=1
pkgdesc="Multiplatform transparent client-side encryption of your files in the cloud."
arch=('x86_64' 'aarch64')
url="https://cryptomator.org/"
license=('GPL3')
depends=('fuse3')
provides=('cryptomator')
conflicts=('cryptomator')
replaces=('cryptomator')
optdepends=('keepassxc-cryptomator: Use KeePassXC to store vault passwords' 'ttf-hanazono: Install this font when using Japanese system language')
source=('org.cryptomator.Cryptomator.desktop'
        'org.cryptomator.Cryptomator.png'
        'org.cryptomator.Cryptomator.svg'
        'org.cryptomator.Cryptomator.tray.svg'
        'org.cryptomator.Cryptomator.tray-unlocked.svg'
        'cryptomator-vault.xml')
source_x86_64=("cryptomator-${pkgver}-${pkgrel}-x86_64.AppImage::https://github.com/cryptomator/cryptomator/releases/download/${pkgver}/cryptomator-${pkgver}-x86_64.AppImage"
               "cryptomator-${pkgver}-${pkgrel}-x86_64.AppImage.asc::https://github.com/cryptomator/cryptomator/releases/download/${pkgver}/cryptomator-${pkgver}-x86_64.AppImage.asc")
source_aarch64=("cryptomator-${pkgver}-${pkgrel}-aarch64.AppImage::https://github.com/cryptomator/cryptomator/releases/download/${pkgver}/cryptomator-${pkgver}-aarch64.AppImage"
                "cryptomator-${pkgver}-${pkgrel}-aarch64.AppImage.asc::https://github.com/cryptomator/cryptomator/releases/download/${pkgver}/cryptomator-${pkgver}-aarch64.AppImage.asc")

sha256sums=('53c509fe54ef1c5c28b469d86291536649367fb2030b2c0fb3101da2031f8e6e'
            'd299636d78d093117fa7a26563f22e01cdb75b1fcc6cc279bc88627574c968bd'
            '0989ecc24ecd672c5c525ab6f1f0fb18a9eeca86ebec19738f512801c152f756'
            '6286d0a409389bc3542ccad53552f85ec5d05422e0c855342304194fd36ccdba'
            '0f815a749d2299ef68b1662e0d5532de96b6b66b5b31cc6aa98a8ae913ccf8be'
            '78537ead26dcc1488d7fff02f47fce559f70f9bb2d7fa7fa1741ad3cd151bfad')
sha256sums_x86_64=('e5d3ecbf4f5d6de095c3e9d926cf8128e667f26e3820e5483a8ffe1e04f04f54'
                   'SKIP')
sha256sums_aarch64=('b65d8f27566e99c61ef52c00233853265ffb7657701b4ec7fb5945bfb2e28aa4'
                    'SKIP')
options=('!strip')

validpgpkeys=('58117AFA1F85B3EEC154677D615D449FE6E6A235')

package() {
  install -Dm755 "${srcdir}/cryptomator-${pkgver}-${pkgrel}-${CARCH}.AppImage" "${pkgdir}/opt/${pkgname}/cryptomator-${pkgver}-${CARCH}.AppImage"
  install -Dm644 "${srcdir}/cryptomator-vault.xml" "${pkgdir}/usr/share/mime/packages/cryptomator-vault.xml"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.desktop" "${pkgdir}/usr/share/applications/org.cryptomator.Cryptomator.desktop"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.png" "${pkgdir}/usr/share/icons/hicolor/scalable/apps/org.cryptomator.Cryptomator.png"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.svg" "${pkgdir}/usr/share/icons/hicolor/512x512/apps/org.cryptomator.Cryptomator.svg"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.tray.svg" "${pkgdir}/usr/share/icons/hicolor/scalable/apps/org.cryptomator.Cryptomator.tray.svg"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.tray-unlocked.svg" "${pkgdir}/usr/share/icons/hicolor/scalable/apps/org.cryptomator.Cryptomator.tray-unlocked.svg"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.tray.svg" "${pkgdir}/usr/share/icons/hicolor/symbolic/apps/org.cryptomator.Cryptomator.tray-symbolic.svg"
  install -Dm644 "${srcdir}/org.cryptomator.Cryptomator.tray-unlocked.svg" "${pkgdir}/usr/share/icons/hicolor/symbolic/apps/org.cryptomator.Cryptomator.tray-unlocked-symbolic.svg"

  mkdir -p "${pkgdir}/usr/bin/"
  ln -s "/opt/${pkgname}/cryptomator-${pkgver}-${CARCH}.AppImage" "${pkgdir}/usr/bin/cryptomator"
}
