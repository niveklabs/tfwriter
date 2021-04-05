# scaleway_rdb_instance

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/scaleway/d/scaleway_rdb_instance"

  # instance_id - (optional) is a type of string
  instance_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(optional) - The ID of the RDB instance"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the database instance"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_rdb_instance" "this" {
  instance_id = var.instance_id
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.certificate
}

output "disable_backup" {
  description = "returns a bool"
  value       = data.scaleway_rdb_instance.this.disable_backup
}

output "endpoint_ip" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.endpoint_ip
}

output "endpoint_port" {
  description = "returns a number"
  value       = data.scaleway_rdb_instance.this.endpoint_port
}

output "engine" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.engine
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.id
}

output "is_ha_cluster" {
  description = "returns a bool"
  value       = data.scaleway_rdb_instance.this.is_ha_cluster
}

output "node_type" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.node_type
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.organization_id
}

output "password" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.password
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.project_id
}

output "read_replicas" {
  description = "returns a list of object"
  value       = data.scaleway_rdb_instance.this.read_replicas
}

output "region" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.region
}

output "settings" {
  description = "returns a map of string"
  value       = data.scaleway_rdb_instance.this.settings
}

output "tags" {
  description = "returns a list of string"
  value       = data.scaleway_rdb_instance.this.tags
}

output "user_name" {
  description = "returns a string"
  value       = data.scaleway_rdb_instance.this.user_name
}

output "this" {
  value = scaleway_rdb_instance.this
}
```

[top](#index)