# oci_blockchain_osn

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_blockchain_osn" {
  source = "./modules/oci/d/oci_blockchain_osn"

  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = null
  # osn_id - (required) is a type of string
  osn_id = null
}
```

[top](#index)

### Variables

```terraform
variable "blockchain_platform_id" {
  description = "(required)"
  type        = string
}

variable "osn_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_blockchain_osn" "this" {
  blockchain_platform_id = var.blockchain_platform_id
  osn_id                 = var.osn_id
}
```

[top](#index)

### Outputs

```terraform
output "ad" {
  description = "returns a string"
  value       = data.oci_blockchain_osn.this.ad
}

output "id" {
  description = "returns a string"
  value       = data.oci_blockchain_osn.this.id
}

output "ocpu_allocation_param" {
  description = "returns a list of object"
  value       = data.oci_blockchain_osn.this.ocpu_allocation_param
}

output "osn_key" {
  description = "returns a string"
  value       = data.oci_blockchain_osn.this.osn_key
}

output "state" {
  description = "returns a string"
  value       = data.oci_blockchain_osn.this.state
}

output "this" {
  value = oci_blockchain_osn.this
}
```

[top](#index)