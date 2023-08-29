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
            '342bcdfa1ca785460e6426a39f527ffa4ba0a77b18eff896e500ff1340c69c35')


package() {
   install -d "$pkgdir/var/cache/pacman/local_repo" 
   install -Dm0644 "${srcdir}/repo-config.conf" "$pkgdir/etc/pacman.d/local_repo/repo-config.conf"
}

