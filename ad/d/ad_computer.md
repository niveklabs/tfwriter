# ad_computer

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
module "ad_computer" {
  source = "./modules/ad/d/ad_computer"

  # dn - (optional) is a type of string
  dn = null
  # guid - (optional) is a type of string
  guid = null
}
```

[top](#index)

### Variables

```terraform
variable "dn" {
  description = "(optional) - The Distinguished Name of the computer object."
  type        = string
  default     = null
}

variable "guid" {
  description = "(optional) - The GUID of the computer object."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ad_computer" "this" {
  dn   = var.dn
  guid = var.guid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ad_computer.this.id
}

output "name" {
  description = "returns a string"
  value       = data.ad_computer.this.name
}

output "this" {
  value = ad_computer.this
}
```

[top](#index)