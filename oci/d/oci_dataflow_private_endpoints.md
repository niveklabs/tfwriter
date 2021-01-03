# oci_dataflow_private_endpoints

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dataflow_private_endpoints" {
  source = "./modules/oci/d/oci_dataflow_private_endpoints"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # display_name_starts_with - (optional) is a type of string
  display_name_starts_with = null
  # owner_principal_id - (optional) is a type of string
  owner_principal_id = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name_starts_with" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner_principal_id" {
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
data "oci_dataflow_private_endpoints" "this" {
  compartment_id           = var.compartment_id
  display_name             = var.display_name
  display_name_starts_with = var.display_name_starts_with
  owner_principal_id       = var.owner_principal_id
  state                    = var.state

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
output "id" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoints.this.id
}

output "private_endpoint_collection" {
  description = "returns a list of object"
  value       = data.oci_dataflow_private_endpoints.this.private_endpoint_collection
}

output "this" {
  value = oci_dataflow_private_endpoints.this
}
```

[top](#index)