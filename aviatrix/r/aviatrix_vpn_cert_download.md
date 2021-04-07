# aviatrix_vpn_cert_download

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_vpn_cert_download" {
  source = "./modules/aviatrix/r/aviatrix_vpn_cert_download"

  # download_enabled - (optional) is a type of bool
  download_enabled = null
  # saml_endpoints - (optional) is a type of set of string
  saml_endpoints = []
}
```

[top](#index)

### Variables

```terraform
variable "download_enabled" {
  description = "(optional) - Whether the VPN Certificate download is enabled. Supported Values: \"true\", \"false\""
  type        = bool
  default     = null
}

variable "saml_endpoints" {
  description = "(optional) - List of SAML endpoint names for which the downloading should be enabled . Currently, only a single endpoint is supported. Example: [\"saml_endpoint_1\"]."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_vpn_cert_download" "this" {
  # download_enabled - (optional) is a type of bool
  download_enabled = var.download_enabled
  # saml_endpoints - (optional) is a type of set of string
  saml_endpoints = var.saml_endpoints
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_vpn_cert_download.this.id
}

output "this" {
  value = aviatrix_vpn_cert_download.this
}
```

[top](#index)