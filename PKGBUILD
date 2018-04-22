# Script generated with Bloom
pkgdesc="ROS - Cartographer is a system that provides real-time simultaneous localization and mapping (SLAM) in 2D and 3D across multiple platforms and sensor configurations. This package provides Cartographer's ROS integration."
url='https://github.com/googlecartographer/cartographer_ros'

pkgname='ros-lunar-cartographer-ros'
pkgver='0.2.0_5'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('gcc'
'gflags'
'gmock'
'google-glog'
'pcl'
'protobuf'
'python2-sphinx'
'ros-lunar-cartographer-ros-msgs'
'ros-lunar-cartographer<0.3.0'
'ros-lunar-catkin'
'ros-lunar-eigen-conversions'
'ros-lunar-geometry-msgs'
'ros-lunar-message-runtime'
'ros-lunar-nav-msgs'
'ros-lunar-pcl-conversions'
'ros-lunar-robot-state-publisher'
'ros-lunar-rosbag'
'ros-lunar-roscpp'
'ros-lunar-roslaunch'
'ros-lunar-roslib'
'ros-lunar-rosunit'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-tf2'
'ros-lunar-tf2-eigen'
'ros-lunar-tf2-ros'
'ros-lunar-urdf'
'ros-lunar-visualization-msgs'
'yaml-cpp'
)

depends=('gflags'
'google-glog'
'pcl'
'ros-lunar-cartographer-ros-msgs'
'ros-lunar-cartographer<0.3.0'
'ros-lunar-eigen-conversions'
'ros-lunar-geometry-msgs'
'ros-lunar-message-runtime'
'ros-lunar-nav-msgs'
'ros-lunar-pcl-conversions'
'ros-lunar-robot-state-publisher'
'ros-lunar-rosbag'
'ros-lunar-roscpp'
'ros-lunar-roslaunch'
'ros-lunar-roslib'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-tf2'
'ros-lunar-tf2-eigen'
'ros-lunar-tf2-ros'
'ros-lunar-urdf'
'ros-lunar-visualization-msgs'
'yaml-cpp'
)

conflicts=()
replaces=()

_dir=cartographer_ros
source=()
md5sums=()

prepare() {
    cp -R $startdir/cartographer_ros $srcdir/cartographer_ros
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

