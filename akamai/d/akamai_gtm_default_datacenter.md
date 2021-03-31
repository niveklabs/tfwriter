# akamai_gtm_default_datacenter

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_gtm_default_datacenter" {
  source = "./modules/akamai/d/akamai_gtm_default_datacenter"

  # datacenter - (optional) is a type of number
  datacenter = null
  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenter" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "akamai_gtm_default_datacenter" "this" {
  datacenter = var.datacenter
  domain     = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "datacenter_id" {
  description = "returns a number"
  value       = data.akamai_gtm_default_datacenter.this.datacenter_id
}

output "id" {
  description = "returns a string"
  value       = data.akamai_gtm_default_datacenter.this.id
}

output "nickname" {
  description = "returns a string"
  value       = data.akamai_gtm_default_datacenter.this.nickname
}

output "this" {
  value = akamai_gtm_default_datacenter.this
}
```

[top](#index)