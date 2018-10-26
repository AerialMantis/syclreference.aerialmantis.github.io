---
layout: page
title: `device` class
permalink: /sycl/host/device
---

| [SYCL][sycl] | [Host API][sycl-host] | [`device`][sycl-host-device] | 
|--------------|-----------------------|------------------------------------------------|

# `device`

The SYCL `device` class encapsulates a single SYCL device on which kernels may be executed. A SYCL device may be an OpenCL device in which case it must encapsulate a valid underlying OpenCL `cl_device_id`, or it may be a SYCL host device in which case it must not.

All member functions of the `device` class are synchronous and errors are handled by throwing synchronous SYCL exceptions.

The default constructor of the SYCL `device` class will construct a host device, while all other constructors construct an OpenCL device.

A SYCL `device` can be partitioned into multiple SYCL devices, by calling the `create_sub_devices()` member function template. The resulting SYCL `device`s are considered sub devices, and it is valid to partition these sub devices further. The range of support for this feature is implementation defined and can be queried for through `get_info()`.

For convenience there are member functions that check the device type. The member function `is_host()` returns true if the SYCL `device` is a host device and the member functions `is_cpu()`, `is_gpu()` and `is_accelerator()` return true if the device type is `info::device_type::cpu`, `info::device_type::gpu` or `info::device_type::accelerator` respectively.

The SYCL `device` class provides the common reference semantics.

## Member functions

| Member function | Description |
|-----------------|-------------|
| [(constructor)][device-constructor] | Constructs an instance of `device`. |
| [(destructor)][device-destructor] | Destructs an instance of `device`. |
| [operator=][device-assignment] | Assigns to an instance of `device` with another instance. |
| [get][device-get] | Returns the `cl_device_id` associated with an instance of `device`. |
| [is_host][device-is-host] | Returns true if an instance of `device` is a host device. |
| [is_cpu][device-is-cpu] | Returns true if an instance of `device` is a CPU device. |
| [is_gpu][device-is-gpu] | Returns true if an instance of `device` is a GPU device. |
| [is_accelerator][device-is-accelerator] | Returns true if an instance of `device` is an accelerator device. |
| [get_platform][device-get-platform] | Returns the `platform` associated with an instance of `device`. |
| [get_info][device-get-info] | Queries an instance of `device` for information. |
| [has_extension][device-has-extension] | Queries an instance of `device` for support for an extension. |
| [create_sub_devices][device-create-sub-devices] | Partitions an instance of `device` into sub-devices. |

## Static member functions

| Static member function | Description |
|------------------------|-------------|
| [get_devices][device-get-devices] | Returns a vector of all `device` instances available within the system. |

## Info Parameters

TODO

[sycl]: ../../
[sycl-host]: ../
[sycl-host-device]: ./