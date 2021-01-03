# ad_gpo

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_gpo" {
  source = "./modules/ad/d/ad_gpo"

  # guid - (optional) is a type of string
  guid = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "guid" {
  description = "(optional) - GUID of the GPO."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the GPO."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ad_gpo" "this" {
  guid = var.guid
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "domain" {
  description = "returns a string"
  value       = data.ad_gpo.this.domain
}

output "id" {
  description = "returns a string"
  value       = data.ad_gpo.this.id
}

output "this" {
  value = ad_gpo.this
}
```

[top](#index)