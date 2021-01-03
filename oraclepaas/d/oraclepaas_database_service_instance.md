# oraclepaas_database_service_instance

[back](../oraclepaas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oraclepaas = ">= 1.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oraclepaas_database_service_instance" {
  source = "./modules/oraclepaas/d/oraclepaas_database_service_instance"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oraclepaas_database_service_instance" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "apex_url" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.apex_url
}

output "availability_domain" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.availability_domain
}

output "backup_destination" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.backup_destination
}

output "bring_your_own_license" {
  description = "returns a bool"
  value       = data.oraclepaas_database_service_instance.this.bring_your_own_license
}

output "character_set" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.character_set
}

output "cloud_storage_container" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.cloud_storage_container
}

output "compute_site_name" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.compute_site_name
}

output "description" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.description
}

output "edition" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.edition
}

output "enterprise_manager_url" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.enterprise_manager_url
}

output "failover_database" {
  description = "returns a bool"
  value       = data.oraclepaas_database_service_instance.this.failover_database
}

output "glassfish_url" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.glassfish_url
}

output "high_performance_storage" {
  description = "returns a bool"
  value       = data.oraclepaas_database_service_instance.this.high_performance_storage
}

output "hybrid_disaster_recovery_ip" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.hybrid_disaster_recovery_ip
}

output "id" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.id
}

output "identity_domain" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.identity_domain
}

output "ip_network" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.ip_network
}

output "ip_reservations" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.ip_reservations
}

output "level" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.level
}

output "listener_port" {
  description = "returns a number"
  value       = data.oraclepaas_database_service_instance.this.listener_port
}

output "monitor_url" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.monitor_url
}

output "national_character_set" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.national_character_set
}

output "pluggable_database_name" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.pluggable_database_name
}

output "region" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.region
}

output "shape" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.shape
}

output "uri" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.uri
}

output "version" {
  description = "returns a string"
  value       = data.oraclepaas_database_service_instance.this.version
}

output "this" {
  value = oraclepaas_database_service_instance.this
}
```

[top](#index)