# bigip_sys_ntp

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_ntp" {
  source = "./modules/bigip/r/bigip_sys_ntp"

  # description - (required) is a type of string
  description = null
  # servers - (optional) is a type of set of string
  servers = []
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - Name of the ntp Servers"
  type        = string
}

variable "servers" {
  description = "(optional) - Servers Address"
  type        = set(string)
  default     = null
}

variable "timezone" {
  description = "(optional) - Servers timezone"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_ntp" "this" {
  description = var.description
  servers     = var.servers
  timezone    = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_sys_ntp.this.id
}

output "this" {
  value = bigip_sys_ntp.this
}
```

[top](#index)