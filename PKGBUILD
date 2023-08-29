# Maintainer: Atolycs
pkgname=aurutils-base
pkgver=1.0.0
pkgrel=1
pkgdesc="AURutils base directory setup meta package"
arch=("any") # 'any' or architecha
url="https://github.com/atolycs"
license=('MIT')
depends=('aurutils' 'pacman-contrib')
#optdepends=('')
#backup=('')
install=create-repo-db.install
source=("repo-config.conf" "create-repo-db.install")
sha256sums=('9e18f0508d5586139be39a10294ac61f8dbb01954f5138ab4d08b710487b9f2e'
            '1fa4f4faf83a173d72aceafa75d7144237532328f2896a239ec28dded08a2316')


package() {
   groupadd --system aurutils
   install -dm3664 "$pkgdir/var/cache/pacman/local_repo" -g aurutils
   install -Dm0644 "${srcdir}/repo-config.conf" "$pkgdir/etc/pacman.d/local_repo/repo-config.conf"
}

