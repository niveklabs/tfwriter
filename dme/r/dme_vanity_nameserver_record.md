# dme_vanity_nameserver_record

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_vanity_nameserver_record" {
  source = "./modules/dme/r/dme_vanity_nameserver_record"

  # default_config - (optional) is a type of bool
  default_config = null
  # name - (required) is a type of string
  name = null
  # name_server_group_id - (optional) is a type of number
  name_server_group_id = null
  # public_config - (optional) is a type of bool
  public_config = null
  # servers - (required) is a type of list of string
  servers = []
}
```

[top](#index)

### Variables

```terraform
variable "default_config" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_server_group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "public_config" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "servers" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "dme_vanity_nameserver_record" "this" {
  default_config       = var.default_config
  name                 = var.name
  name_server_group_id = var.name_server_group_id
  public_config        = var.public_config
  servers              = var.servers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dme_vanity_nameserver_record.this.id
}

output "this" {
  value = dme_vanity_nameserver_record.this
}
```

[top](#index)