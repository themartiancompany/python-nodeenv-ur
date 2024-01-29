# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Felix Yan <felixonmars@archlinux.org>

pkgname=python-nodeenv
pkgver=1.8.0
pkgrel=1
pkgdesc="Node.js virtual environment builder"
url="https://github.com/ekalinin/nodeenv"
license=('BSD')
arch=('any')
depends=('python-setuptools' 'make')
optdepends=('nodejs: for --node=system')
checkdepends=('nodejs' 'python-pytest-runner' 'python-coverage')
source=("$pkgname-$pkgver.tar.gz::https://github.com/ekalinin/nodeenv/archive/$pkgver.tar.gz")
sha512sums=('96dce219e00d3837b2b0083af9fe6d94ed4e3cd029e3da564263ad8656dcb9c52440c2df6a6954095e5cacd03e44437f08695603dea82c28122713045183014f')

build() {
  cd nodeenv-$pkgver
  python setup.py build
}

check() {
  cd nodeenv-$pkgver
  python setup.py pytest
}

package() {
  cd nodeenv-$pkgver
  python setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 LICENSE -t "$pkgdir"/usr/share/licenses/$pkgname/
}

# vim:set sw=2 sts=-1 et:
