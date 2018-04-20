# Script generated with Bloom
pkgdesc="ROS - ROS messages packages for the ROBOTIS RH-P12-RN (meta package)"
url='http://wiki.ros.org/rh_p12_rn'

pkgname='ros-kinetic-rh-p12-rn'
pkgver='0.1.0_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-rh-p12-rn-base-module'
'ros-kinetic-rh-p12-rn-base-module-msgs'
'ros-kinetic-rh-p12-rn-description'
'ros-kinetic-rh-p12-rn-gazebo'
'ros-kinetic-rh-p12-rn-gui'
'ros-kinetic-rh-p12-rn-manager'
)

conflicts=()
replaces=()

_dir=rh_p12_rn
source=()
md5sums=()

prepare() {
    cp -R $startdir/rh_p12_rn $srcdir/rh_p12_rn
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

