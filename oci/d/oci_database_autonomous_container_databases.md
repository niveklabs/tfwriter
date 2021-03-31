# oci_database_autonomous_container_databases

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_container_databases" {
  source = "./modules/oci/d/oci_database_autonomous_container_databases"

  # autonomous_exadata_infrastructure_id - (optional) is a type of string
  autonomous_exadata_infrastructure_id = null
  # autonomous_vm_cluster_id - (optional) is a type of string
  autonomous_vm_cluster_id = null
  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # infrastructure_type - (optional) is a type of string
  infrastructure_type = null
  # service_level_agreement_type - (optional) is a type of string
  service_level_agreement_type = null
  # state - (optional) is a type of string
  state = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_exadata_infrastructure_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autonomous_vm_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "infrastructure_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_level_agreement_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_container_databases" "this" {
  autonomous_exadata_infrastructure_id = var.autonomous_exadata_infrastructure_id
  autonomous_vm_cluster_id             = var.autonomous_vm_cluster_id
  availability_domain                  = var.availability_domain
  compartment_id                       = var.compartment_id
  display_name                         = var.display_name
  infrastructure_type                  = var.infrastructure_type
  service_level_agreement_type         = var.service_level_agreement_type
  state                                = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "autonomous_container_databases" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_container_databases.this.autonomous_container_databases
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_databases.this.id
}

output "this" {
  value = oci_database_autonomous_container_databases.this
}
```

[top](#index)