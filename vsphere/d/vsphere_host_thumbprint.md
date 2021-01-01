# vsphere_host_thumbprint

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "vsphere_host_thumbprint" {
  source = "./modules/vsphere/d/vsphere_host_thumbprint"

  # address - (required) is a type of string
  address = null
  # insecure - (optional) is a type of bool
  insecure = null
  # port - (optional) is a type of string
  port = null
}
```

[top](#index)

### Variables

```hcl
variable "address" {
  description = "(required) - The address of the ESXi to extract the thumbprint from."
  type        = string
}

variable "insecure" {
  description = "(optional) - Boolean that can be set to true to disable SSL certificate verification."
  type        = bool
  default     = null
}

variable "port" {
  description = "(optional) - The port to connect to on the ESXi host."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_host_thumbprint" "this" {
  address  = var.address
  insecure = var.insecure
  port     = var.port
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.vsphere_host_thumbprint.this.id
}

output "this" {
  value = vsphere_host_thumbprint.this
}
```

[top](#index)