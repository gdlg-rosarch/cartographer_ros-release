# Script generated with Bloom
pkgdesc="ROS - Cartographer is a system that provides real-time simultaneous localization and mapping (SLAM) in 2D and 3D across multiple platforms and sensor configurations. This package provides Cartographer's RViz integration."
url='https://github.com/googlecartographer/cartographer_ros'

pkgname='ros-lunar-cartographer-rviz'
pkgver='0.2.0_5'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('gcc'
'qt5-base'
'ros-lunar-cartographer-ros'
'ros-lunar-cartographer-ros-msgs'
'ros-lunar-cartographer<0.3.0'
'ros-lunar-catkin'
'ros-lunar-eigen-conversions'
'ros-lunar-message-runtime'
'ros-lunar-roscpp'
'ros-lunar-roslib'
'ros-lunar-rviz'
)

depends=('qt5-base'
'ros-lunar-cartographer-ros'
'ros-lunar-cartographer-ros-msgs'
'ros-lunar-cartographer<0.3.0'
'ros-lunar-eigen-conversions'
'ros-lunar-message-runtime'
'ros-lunar-roscpp'
'ros-lunar-roslib'
'ros-lunar-rviz'
)

conflicts=()
replaces=()

_dir=cartographer_rviz
source=()
md5sums=()

prepare() {
    cp -R $startdir/cartographer_rviz $srcdir/cartographer_rviz
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

