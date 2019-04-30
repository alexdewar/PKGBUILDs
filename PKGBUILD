# Maintainer: Alex Dewar <a.dewar@sussex.ac.uk>
pkgname=genn_cpu_only
pkgver=4.0.0_RC1
pkgrel=1
pkgdesc="GeNN: GPU-enhanced neural networks (version 4, without CUDA support)"
arch=(x86_64)
url="https://github.com/genn-team/genn"
license=('GPL')
makedepends=(doxygen)
provides=(genn)
conflicts=(genn)
options=(staticlibs !emptydirs)
source=("$url/archive/${pkgver//_/-}.tar.gz")
sha256sums=('b94c0b8c05d8525987f9d4279478dd41f68e8d9824cb5344adb5fbe257b38e99')

build() {
	cd genn-${pkgver//_/-}

	# Generate documentation with doxygen
	./makedoc

	# Build libgenn.a etc.
	sed -i 's|/usr/local|'$pkgdir'/usr|' Makefile
	CPU_ONLY=1 CUDA_PATH= make
}

package() {
	cd genn-${pkgver//_/-}

	# Install libs and headers
	CPU_ONLY=1 CUDA_PATH= PREFIX="$pkgdir"/usr/ make install

	# Install documentation
	mkdir -p "$pkgdir"/usr/share/genn/documentation
	cp -rf documentation/html/* "$pkgdir"/usr/share/genn/documentation
}
