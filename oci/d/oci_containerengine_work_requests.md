# oci_containerengine_work_requests

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_containerengine_work_requests" {
  source = "./modules/oci/d/oci_containerengine_work_requests"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # resource_id - (optional) is a type of string
  resource_id = null
  # resource_type - (optional) is a type of string
  resource_type = null
  # status - (optional) is a type of list of string
  status = []

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
variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = list(string)
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
data "oci_containerengine_work_requests" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # resource_id - (optional) is a type of string
  resource_id = var.resource_id
  # resource_type - (optional) is a type of string
  resource_type = var.resource_type
  # status - (optional) is a type of list of string
  status = var.status

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
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
  value       = data.oci_containerengine_work_requests.this.id
}

output "work_requests" {
  description = "returns a list of object"
  value       = data.oci_containerengine_work_requests.this.work_requests
}

output "this" {
  value = oci_containerengine_work_requests.this
}
```

[top](#index)