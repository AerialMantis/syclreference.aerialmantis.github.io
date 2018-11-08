---
layout: page
title: `device` class
permalink: /sycl/host/device
---

| [SYCL][sycl] > [Host API][sycl-host] > [`cl::sycl::device`][sycl-host-device] |

# `cl::sycl::device`

---

Defined in header <CL/sycl.hpp>

---


```cpp
namespace cl {
namespace sycl {

class device;

}  // namespace sycl
}  // namespace cl
```

***

The `device` class encapsulates a single *SYCL device* on which a *SYCL kernel* may be executed. A *SYCL device* may be an *OpenCL device* in which case it must encapsulate a valid underlying OpenCL `cl_device_id`, or it may be a *SYCL host device* in which case it must not.

The default constructor of the SYCL `device` class will construct a host device, while all other constructors construct an OpenCL device.

A SYCL `device` can be partitioned into multiple SYCL devices, by calling the `create_sub_devices()` member function template. The resulting SYCL `device`s are considered sub devices, and it is valid to partition these sub devices further. The range of support for this feature is implementation defined and can be queried for through `get_info()`.

For convenience there are member functions that check the device type. The member function `is_host()` returns true if the SYCL `device` is a host device and the member functions `is_cpu()`, `is_gpu()` and `is_accelerator()` return true if the device type is `info::device_type::cpu`, `info::device_type::gpu` or `info::device_type::accelerator` respectively.

All member functions of the `device` class are synchronous and errors are handled by throwing synchronous SYCL exceptions.

***

## Member functions

| Member function | Description |
|-----------------|-------------|
| [(constructor)][sycl-host-device-constructor] | Constructs an instance of `device`. |
| [(destructor)][sycl-host-device-destructor] | Destructs an instance of `device`. |
| [operator=][sycl-host-device-assignment] | Assigns to an instance of `device` with another instance. |
| [get][sycl-host-device-get] | Returns the `cl_device_id` associated with an instance of `device`. |
| [is_host][sycl-host-device-is-host] | Returns true if an instance of `device` is a host device. |
| [is_cpu][sycl-host-device-is-cpu] | Returns true if an instance of `device` is a CPU device. |
| [is_gpu][sycl-host-device-is-gpu] | Returns true if an instance of `device` is a GPU device. |
| [is_accelerator][sycl-host-device-is-accelerator] | Returns true if an instance of `device` is an accelerator device. |
| [get_platform][sycl-host-device-get-platform] | Returns the `platform` associated with an instance of `device`. |
| [get_info][sycl-host-device-get-info] | Queries an instance of `device` for information. |
| [has_extension][sycl-host-device-has-extension] | Queries an instance of `device` for support for an extension. |
| [create_sub_devices][sycl-host-device-create-sub-devices] | Partitions an instance of `device` into sub-devices. |

## Static member functions

| Static member function | Description |
|------------------------|-------------|
| [get_devices][sycl-host-device-get-devices] | Returns a vector of all `device` instances available within the system. |

## Info Parameters

| Info Parameter | Return Type | Description |
|----------------|-------------|-------------|
| cl::sycl::device::info::device_type | info::device_type | cl_uint | TODO |
| cl::sycl::device::info::vendor_id | cl_uint | TODO |
| cl::sycl::device::info::max_compute_units | cl_uint | TODO |
| cl::sycl::device::info::max_work_item_sizes | cl::sycl::id<3> | TODO |
| cl::sycl::device::info::max_work_group_size | size_t | TODO |
| cl::sycl::device::info::preferred_vector_width_char | cl_uint | TODO |
| cl::sycl::device::info::preferred_vector_width_short | cl_uint | TODO |
| cl::sycl::device::info::preferred_vector_width_int | cl_uint | TODO |
| cl::sycl::device::info::preferred_vector_width_long | cl_uint | TODO |
| cl::sycl::device::info::preferred_vector_width_float | cl_uint | TODO |
| cl::sycl::device::info::preferred_vector_width_double | cl_uint | TODO |
| cl::sycl::device::info::preferred_vector_width_half | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_char | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_short | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_int | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_long | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_float | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_double | cl_uint | TODO |
| cl::sycl::device::info::native_vector_width_half | cl_uint | TODO |

## Example

TODO

[sycl]: ../../
[sycl-host]: ../
[sycl-host-device]: ./

[sycl-host-device-constructor]: ./constructor
[sycl-host-device-destructor]: ./destructor
[sycl-host-device-assignment]: ./assignment
[sycl-host-device-get]: ./get
[sycl-host-device-is-host]: ./is_host
[sycl-host-device-is-cpu]: ./is_cpu
[sycl-host-device-is-gpu]: ./is_gpu
[sycl-host-device-is-accelerator]: ./is_accelerator
[sycl-host-device-get-platform]: ./get_platform
[sycl-host-device-get-info]: ./get_info
[sycl-host-device-has-extension]: ./has_extension
[sycl-host-device-create-sub-devices]: ./create_sub_devices

[sycl-host-device-get-devices]: ./get_devices