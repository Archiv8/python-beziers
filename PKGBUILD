#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-beziers/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-beziers/discussions>

_langname="python"
_relname="beziers"

pkgname="${_langname}-${_relname}"
pkgver=0.4.0
pkgrel=1
pkgdesc="Routines for extracting information from font glyphs"
arch=(
  "any"
)
url="https://github.com/simoncozens/beziers.py"
license=(
  "MIT"
)
depends=(
  "python"
)
makedepends=(
  "python-build"
  "python-installer"
  "python-setuptools"
  "python-wheel"
)
_tarname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz"
)
sha512sums=(
  "7568417e559c516bb37fc30f68be78ce9ba11282e8ebb1c1ae87409d1a1d560252da67566dab25069390c4b72d7164942bcd7494a6ac3017e401796a7a58e362"
)

build() {

  cd "${_tarname}"

  python -m build -wn
}

package() {

  cd "$_tarname"

  python -m installer -d "${pkgdir}" dist/*.whl

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE
}
