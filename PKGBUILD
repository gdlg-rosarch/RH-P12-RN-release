# Script generated with Bloom
pkgdesc="ROS - This package provides GUI interface to control the RH-P12-RN"
url='http://wiki.ros.org/rh_p12_rn_gui'

pkgname='ros-kinetic-rh-p12-rn-gui'
pkgver='0.1.0_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('qt4'
'ros-kinetic-catkin'
'ros-kinetic-qt-build'
'ros-kinetic-rh-p12-rn-base-module-msgs'
'ros-kinetic-robotis-controller-msgs'
'ros-kinetic-roscpp'
)

depends=('qt4'
'ros-kinetic-qt-build'
'ros-kinetic-rh-p12-rn-base-module-msgs'
'ros-kinetic-robotis-controller-msgs'
'ros-kinetic-roscpp'
)

conflicts=()
replaces=()

_dir=rh_p12_rn_gui
source=()
md5sums=()

prepare() {
    cp -R $startdir/rh_p12_rn_gui $srcdir/rh_p12_rn_gui
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

