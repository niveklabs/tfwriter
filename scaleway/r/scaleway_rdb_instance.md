# scaleway_rdb_instance

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_rdb_instance" {
  source = "./modules/scaleway/r/scaleway_rdb_instance"

  # disable_backup - (optional) is a type of bool
  disable_backup = null
  # engine - (required) is a type of string
  engine = null
  # is_ha_cluster - (optional) is a type of bool
  is_ha_cluster = null
  # name - (optional) is a type of string
  name = null
  # node_type - (required) is a type of string
  node_type = null
  # password - (optional) is a type of string
  password = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # settings - (optional) is a type of map of string
  settings = {}
  # tags - (optional) is a type of list of string
  tags = []
  # user_name - (optional) is a type of string
  user_name = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "disable_backup" {
  description = "(optional) - Disable automated backup for the database instance"
  type        = bool
  default     = null
}

variable "engine" {
  description = "(required) - Database's engine version id"
  type        = string
}

variable "is_ha_cluster" {
  description = "(optional) - Enable or disable high availability for the database instance"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Name of the database instance"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(required) - The type of database instance you want to create"
  type        = string
}

variable "password" {
  description = "(optional) - Password for the first user of the database instance"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "settings" {
  description = "(optional) - Map of engine settings to be set."
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional) - List of tags [\"tag1\", \"tag2\", ...] attached to a database instance"
  type        = list(string)
  default     = null
}

variable "user_name" {
  description = "(optional) - Identifier for the first user of the database instance"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_rdb_instance" "this" {
  # disable_backup - (optional) is a type of bool
  disable_backup = var.disable_backup
  # engine - (required) is a type of string
  engine = var.engine
  # is_ha_cluster - (optional) is a type of bool
  is_ha_cluster = var.is_ha_cluster
  # name - (optional) is a type of string
  name = var.name
  # node_type - (required) is a type of string
  node_type = var.node_type
  # password - (optional) is a type of string
  password = var.password
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # region - (optional) is a type of string
  region = var.region
  # settings - (optional) is a type of map of string
  settings = var.settings
  # tags - (optional) is a type of list of string
  tags = var.tags
  # user_name - (optional) is a type of string
  user_name = var.user_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.certificate
}

output "endpoint_ip" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.endpoint_ip
}

output "endpoint_port" {
  description = "returns a number"
  value       = scaleway_rdb_instance.this.endpoint_port
}

output "id" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.project_id
}

output "read_replicas" {
  description = "returns a list of object"
  value       = scaleway_rdb_instance.this.read_replicas
}

output "region" {
  description = "returns a string"
  value       = scaleway_rdb_instance.this.region
}

output "settings" {
  description = "returns a map of string"
  value       = scaleway_rdb_instance.this.settings
}

output "this" {
  value = scaleway_rdb_instance.this
}
```

[top](#index)