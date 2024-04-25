# Project

This project includes a utility to help identify Azure NVMe devices.

## Quick Start

To build:

```
cmake .
make
```

To install /usr/local/bin/azure-nvme-id and /usr/local/lib/udev/rules.d/80-azure-nvme.rules:

```
sudo make install
```

To run:

```
sudo azure-nvme-id
```

To run in udev mode:

```
DEVNAME=/dev/nvme0n1 azure-nvme-id --udev
```

### Enabling LUN Calculation by Namespace Identifier (Default)

The "LUN" configured by the user for data disks can be computed by the namespace identifier for "MSFT NVMe Accelerator v1.0" controllers.

This is currently enabled by default to support cases where there is no identification information available in the vendor-specific field of Identify Namespace data structure.

It can be explicitly enabled by passing AZURE_LUN_CALCULATION_BY_NSID_ENABLED=1 to cmake:

```
cmake -DAZURE_LUN_CALCULATION_BY_NSID_ENABLED=1 .
```

## Disabling LUN Calculation by Namespace Identifier

Pass AZURE_LUN_CALCULATION_BY_NSID_ENABLED=0 to cmake:

```
cmake -DAZURE_LUN_CALCULATION_BY_NSID_ENABLED=0 .
```

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
