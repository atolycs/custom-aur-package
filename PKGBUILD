# Maintainer: Atolycs
pkgname=vscode-server
pkgver="1.82.2"
pkgrel=1
pkgdesc="Official Visual Studio Code server"
arch=(x86_64) # 'any' or architecha
url="https://az764295.vo.msecnd.net/stable"
license=('')
depends=('tar' 'xz' 'curl' 'jq' 'gzip')
#optdepends=('')
#backup=('')
__stable_hash=$(curl https://update.code.visualstudio.com/api/commits/stable/server-linux-x64-web | jq '.[0]' | sed -e 's/"//g')

source=("vscode-server.service"
     "${url}/${__stable_hash}/vscode-server-linux-x64-web.tar.gz"
)
sha256sums=('b7f527ac6d720ccf04d6802df00c991bf3be036b70378893317918bcb24be063'
            '4fc64900643508f70901fc66e32d6f86ad4f4e725183ab896dcfba99b442b889')

pkgver() {
  printf "%s" $(curl -s "https://api.github.com/repos/microsoft/vscode/releases" | jq '.[0].tag_name')
}

#build() {
#}

package() {
   mkdir -p "$pkgdir/opt"
   mv "vscode-server-linux-x64-web" "$pkgdir/opt/$pkgname"

   mkdir -p "$pkgdir/usr/bin"
   ln -s "/opt/$pkgname/bin/code-server" "$pkgdir/usr/bin/code-server"

   mkdir -p "$pkgdir/usr/lib/systemd/user"
   install -Dm644 "$pkgname.service" -t "$pkgdir/usr/lib/systemd/user/"

   mkdir -p "$pkgdir/usr/share/licenses"
   install -Dm644 "$pkgdir/opt/vscode-server/LICENSE" -t "$pkgdir/usr/share/licenses/"
}

