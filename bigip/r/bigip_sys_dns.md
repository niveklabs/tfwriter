# bigip_sys_dns

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
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_dns" {
  source = "./modules/bigip/r/bigip_sys_dns"

  # description - (required) is a type of string
  description = null
  # name_servers - (optional) is a type of set of string
  name_servers = []
  # number_of_dots - (optional) is a type of number
  number_of_dots = null
  # search - (optional) is a type of set of string
  search = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - Name of the Dns Servers"
  type        = string
}

variable "name_servers" {
  description = "(optional) - Servers Address"
  type        = set(string)
  default     = null
}

variable "number_of_dots" {
  description = "(optional) - how many DNS Servers"
  type        = number
  default     = null
}

variable "search" {
  description = "(optional) - Servers search domain"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_dns" "this" {
  description    = var.description
  name_servers   = var.name_servers
  number_of_dots = var.number_of_dots
  search         = var.search
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_sys_dns.this.id
}

output "this" {
  value = bigip_sys_dns.this
}
```

[top](#index)