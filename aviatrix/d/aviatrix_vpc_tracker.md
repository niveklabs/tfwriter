# aviatrix_vpc_tracker

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_vpc_tracker" {
  source = "./modules/aviatrix/d/aviatrix_vpc_tracker"

  # account_name - (optional) is a type of string
  account_name = null
  # cidr - (optional) is a type of string
  cidr = null
  # cloud_type - (optional) is a type of number
  cloud_type = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(optional) - Get VPCs that match the given access account name."
  type        = string
  default     = null
}

variable "cidr" {
  description = "(optional) - Get VPCs that match the given CIDR."
  type        = string
  default     = null
}

variable "cloud_type" {
  description = "(optional) - Get VPCs from a single cloud provider. For example, if cloud_type = 4, only GCP VPCs will be returned."
  type        = number
  default     = null
}

variable "region" {
  description = "(optional) - Get VPCs that match the given region."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_vpc_tracker" "this" {
  account_name = var.account_name
  cidr         = var.cidr
  cloud_type   = var.cloud_type
  region       = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aviatrix_vpc_tracker.this.id
}

output "vpc_list" {
  description = "returns a list of object"
  value       = data.aviatrix_vpc_tracker.this.vpc_list
}

output "this" {
  value = aviatrix_vpc_tracker.this
}
```

[top](#index)