# Maintainer: Kimiblock Moe
_name="Amulet-Core"
pkgname=python-amulet-core
pkgdesc="A Python library for reading and writing the Minecraft save formats. See Amulet for the actual editor."
url="https://github.com/Amulet-Team/Amulet-Core"
license=(unknown)
arch=(any)
pkgver=1.9.21
pkgrel=1
makedepends=(python-build python-installer python-wheel)
depends=(python python-amulet-nbt python-numpy python-pymctranslate python-versioneer python-portalocker python-leveldb python-amulet-leveldb)
source=(
	"${pkgname}-${pkgver}"::"https://github.com/Amulet-Team/Amulet-Core/archive/refs/tags/${pkgver}.tar.gz"
)
md5sums=(
	"042ac0dd6f499ef462cb8d21a6182ddc"
)

function prepare() {
	sed -i 's/versioneer-518/versioneer/g' "${srcdir}/${_name}-${pkgver}/pyproject.toml"
}

function build() {
	cd "${srcdir}/${_name}-${pkgver}"
	python -m build --wheel --no-isolation
}

function package() {
	cd "${srcdir}/${_name}-${pkgver}"
	python -m installer --destdir="${pkgdir}" dist/*.whl
}
