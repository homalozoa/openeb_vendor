# openeb_vendor
[![License](https://img.shields.io/badge/License-Apache%202.0-orange)](https://choosealicense.com/licenses/apache-2.0/)
[![foxy](https://github.com/homalozoa/openeb_vendor/actions/workflows/foxy.yaml/badge.svg)](https://github.com/homalozoa/openeb_vendor/actions/workflows/foxy.yaml)
[![galactic](https://github.com/homalozoa/openeb_vendor/actions/workflows/galactic.yaml/badge.svg)](https://github.com/homalozoa/openeb_vendor/actions/workflows/galactic.yaml)
[![rolling](https://github.com/homalozoa/openeb_vendor/actions/workflows/rolling.yaml/badge.svg)](https://github.com/homalozoa/openeb_vendor/actions/workflows/rolling.yaml)

## Introduction

ROS 2 vendor package for [openeb](https://github.com/prophesee-ai/openeb)

## Building

Make sure you have sourced ROS 2 environment. If not, do

```
source /opt/ros/<replace your ROS 2 distro version here>/setup.sh
```

Then clone this repo, and check dependencies to make sure all depends library are installed.

```
mkdir -p evt_ws/src
cd evt_ws/src
git clone https://github.com/homalozoa/openeb_vendor.git
cd ..
rosdep install --from-paths src --ignore-src -r -y
```

Make sure all installations are succeed.

Then, just build this package with `colcon`

```
colcon build
```

or

```
colcon build --merge-install
```

## License

This is just a vendor package for [openeb](https://github.com/prophesee-ai/openeb), hince all copyright of source code in `openeb` is belong to its project. The license of this repo is `Apache License 2.0`.
