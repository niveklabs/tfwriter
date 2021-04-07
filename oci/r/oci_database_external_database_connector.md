# oci_database_external_database_connector

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_external_database_connector" {
  source = "./modules/oci/r/oci_database_external_database_connector"

  # connector_agent_id - (required) is a type of string
  connector_agent_id = null
  # connector_type - (optional) is a type of string
  connector_type = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # external_database_id - (required) is a type of string
  external_database_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

  connection_credentials = [{
    credential_name = null
    credential_type = null
    password        = null
    role            = null
    username        = null
  }]

  connection_string = [{
    hostname = null
    port     = null
    protocol = null
    service  = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connector_agent_id" {
  description = "(required)"
  type        = string
}

variable "connector_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "external_database_id" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "connection_credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      credential_name = string
      credential_type = string
      password        = string
      role            = string
      username        = string
    }
  ))
}

variable "connection_string" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      hostname = string
      port     = number
      protocol = string
      service  = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_external_database_connector" "this" {
  # connector_agent_id - (required) is a type of string
  connector_agent_id = var.connector_agent_id
  # connector_type - (optional) is a type of string
  connector_type = var.connector_type
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # external_database_id - (required) is a type of string
  external_database_id = var.external_database_id
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags

  dynamic "connection_credentials" {
    for_each = var.connection_credentials
    content {
      # credential_name - (optional) is a type of string
      credential_name = connection_credentials.value["credential_name"]
      # credential_type - (optional) is a type of string
      credential_type = connection_credentials.value["credential_type"]
      # password - (optional) is a type of string
      password = connection_credentials.value["password"]
      # role - (optional) is a type of string
      role = connection_credentials.value["role"]
      # username - (optional) is a type of string
      username = connection_credentials.value["username"]
    }
  }

  dynamic "connection_string" {
    for_each = var.connection_string
    content {
      # hostname - (required) is a type of string
      hostname = connection_string.value["hostname"]
      # port - (required) is a type of number
      port = connection_string.value["port"]
      # protocol - (required) is a type of string
      protocol = connection_string.value["protocol"]
      # service - (required) is a type of string
      service = connection_string.value["service"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.compartment_id
}

output "connection_status" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.connection_status
}

output "connector_type" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.connector_type
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_external_database_connector.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_external_database_connector.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.state
}

output "time_connection_status_last_updated" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.time_connection_status_last_updated
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_external_database_connector.this.time_created
}

output "this" {
  value = oci_database_external_database_connector.this
}
```

[top](#index)