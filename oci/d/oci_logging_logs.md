# oci_logging_logs

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_logging_logs" {
  source = "./modules/oci/d/oci_logging_logs"

  # display_name - (optional) is a type of string
  display_name = null
  # log_group_id - (required) is a type of string
  log_group_id = null
  # log_type - (optional) is a type of string
  log_type = null
  # source_resource - (optional) is a type of string
  source_resource = null
  # source_service - (optional) is a type of string
  source_service = null
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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_group_id" {
  description = "(required)"
  type        = string
}

variable "log_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_resource" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_service" {
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
data "oci_logging_logs" "this" {
  display_name    = var.display_name
  log_group_id    = var.log_group_id
  log_type        = var.log_type
  source_resource = var.source_resource
  source_service  = var.source_service
  state           = var.state

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
  value       = data.oci_logging_logs.this.id
}

output "logs" {
  description = "returns a list of object"
  value       = data.oci_logging_logs.this.logs
}

output "this" {
  value = oci_logging_logs.this
}
```

[top](#index)