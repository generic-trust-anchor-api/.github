# Generic trust anchor application programming interface for industrial IoT devices

## Introduction
This project provides an open-source implementation of the Generic trust anchor API for
industrial IoT devices (GTA API) as specified by [ISO/IEC TS 30168](https://www.iso.org/standard/53288.html).

This implementation of ISO/IEC TS 30168 can be used as a basis or reference
to either enhance the open-source implementation or create own implementations
of the GTA API.

The current implementation provides
- a general core framework for GTA API.
- a software-based provider for GTA API.

Using these two components it is possible to build and run your first GTA API example applications. Please refer to the software provider repository for more information about the [supported profiles]( https://github.com/generic-trust-anchor-api/gta-api-sw-provider?tab=readme-ov-file#supported-profiles).

Licensing information can be found in the respective GTA API repositories and their dependencies.

## GTA API core framework
The repository [gta-api-core](https://github.com/generic-trust-anchor-api/gta-api-core) contains an example implementation for the basic functionality that has to be provided by the GTA API framework as described in ISO/IEC TS 30168 Figure 2.

The current implementation targets a Un*x like environment.

## GTA API software provider
The repository [gta-api-sw-provider](https://github.com/generic-trust-anchor-api/gta-api-sw-provider) contains an example implementation for a secure element provider for GTA API. The implementation is software-only, i.e., there is no protection by a hardware secure element. The motivation for the GTA API software provider is to provide a starting point to get familiar with GTA API but it is **not intended for productive use**.

Nevertheless, the software provider is prepared to achieve a minimal security level by protecting its persisted state (i.e., device state, personalities, further metadata) with a hardware unique key. Please refer to the repository for more details.

The GTA API software provider allows to develop an application which is based on the GTA API interfaces without having a secure element. The GTA API software provider can then be enhanced (e.g., by providing a hardware unique key) or replaced by another provider supporting some hardware secure element at a later stage.

The cryptographic functions are computed using the [OpenSSL](https://openssl-library.org/) library as 3rd party cryptographic service provider.

