# Transforms

Header-only library for S3 and SE(3) object implementations.

To include in your project, add the following lines to your *CMakeLists.txt* file:

```cmake
include_directories(path/to/transforms/include)
add_subdirectory(path/to/transforms)
```

# Example Usages

## Quaternions

```c++
#include "transforms/quat.h"
using namespace quat;
```

Initialize a quaternion:

```c++
Eigen::Vector3d v;
v << 1, 0, 0;
Quatd q = Quatd::from_axis_angle(v, 0.0);
Quatd q = Quatd::Random();
Quatd q = Quatd::from_two_unit_vectors(v1, v2);
Eigen::Matrix3d R;
Quatd q = Quatd::from_R(R);
Quatd q = Quatd::Identity();
Eigen::Vector3d omega;
Quatd q = Quatd::exp(omega);
Quatd q2 = q.copy();
double roll, pitch, yaw;
Quatd q = Quatd::from_euler(roll, pitch, yaw);
```

## Xform

Include the xform class:

```c++
#include "transforms/xform.h"
using namespace xform;
```

Initialize a transform:

```c++
xform::Xformd T((Vector3d() << 1, 1, 0).finished(),
                Quatd::from_axis_angle((Vector3d() << 0, 0, 1).finished(), M_PI/4.0));
```
