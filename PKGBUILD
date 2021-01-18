# Maintainer: Alex Dewar <a.dewar@sussex.ac.uk>
# Maintainer: Doron Cohen <me@doron.dev>

pkgname=antidot-bin
pkgdesc="Cleans up your $HOME from those pesky dotfiles"
url="https://github.com/doron-cohen/antidot"
license=("MIT")
arch=("x86_64")

pkgver=0.5.0
pkgrel=5

provides=("antidot")
conflicts=("antidot")
depends=()

source=("antidot-0.5.0.bin::https://github.com/doron-cohen/antidot/releases/download/v0.5.0/antidot_0.5.0_linux_amd64")
sha256sums=("8e6231ab542621b4f30bca03856c04a3b0911aec36f0080e6972aa4e211cc1b7")

package() {
  install -Dm 0755 "$srcdir/antidot-0.5.0.bin" "$pkgdir/usr/bin/antidot"
}
