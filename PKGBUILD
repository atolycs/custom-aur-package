# Maintainer: Atolycs
pkgname=paccache-hook
pkgver=1.0.0
pkgrel=1
pkgdesc="paccache Hook script"
arch=('any') # 'any' or architecha
url=""
license=('MIT')
depends=('pacman-contrib')
#optdepends=('')
backup=('etc/pacman.d/hooks/80-paccache.hook')
source=("paccache.hook")
sha256sums=('2b901834aef2839e4ec4e6bcd5d0f0f75112eaff66f5f7772e040a2bb8fb417d')

package() {
  install -Dm0644 "${srcdir}/paccache.hook" "${pkgdir}/etc/pacman.d/hooks/80-paccache.hook"
}

