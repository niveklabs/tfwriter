# dme_vanity_nameserver_record

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_vanity_nameserver_record" {
  source = "./modules/dme/d/dme_vanity_nameserver_record"

  # default_config - (optional) is a type of string
  default_config = null
  # name - (required) is a type of string
  name = null
  # name_server_group_id - (optional) is a type of string
  name_server_group_id = null
  # public_config - (optional) is a type of string
  public_config = null
  # servers - (optional) is a type of list of string
  servers = []
}
```

[top](#index)

### Variables

```terraform
variable "default_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_server_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "dme_vanity_nameserver_record" "this" {
  # default_config - (optional) is a type of string
  default_config = var.default_config
  # name - (required) is a type of string
  name = var.name
  # name_server_group_id - (optional) is a type of string
  name_server_group_id = var.name_server_group_id
  # public_config - (optional) is a type of string
  public_config = var.public_config
  # servers - (optional) is a type of list of string
  servers = var.servers
}
```

[top](#index)

### Outputs

```terraform
output "default_config" {
  description = "returns a string"
  value       = data.dme_vanity_nameserver_record.this.default_config
}

output "id" {
  description = "returns a string"
  value       = data.dme_vanity_nameserver_record.this.id
}

output "name_server_group_id" {
  description = "returns a string"
  value       = data.dme_vanity_nameserver_record.this.name_server_group_id
}

output "public_config" {
  description = "returns a string"
  value       = data.dme_vanity_nameserver_record.this.public_config
}

output "servers" {
  description = "returns a list of string"
  value       = data.dme_vanity_nameserver_record.this.servers
}

output "this" {
  value = dme_vanity_nameserver_record.this
}
```

[top](#index)