# bigip_ltm_datagroup

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_datagroup" {
  source = "./modules/bigip/d/bigip_ltm_datagroup"

  # name - (required) is a type of string
  name = null
  # partition - (required) is a type of string
  partition = null
  # type - (optional) is a type of string
  type = null

  record = [{
    data = null
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the Data Group List"
  type        = string
}

variable "partition" {
  description = "(required) - partition of resource group"
  type        = string
}

variable "type" {
  description = "(optional) - The Data Group type (string, ip, integer)"
  type        = string
  default     = null
}

variable "record" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      data = string
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "bigip_ltm_datagroup" "this" {
  name      = var.name
  partition = var.partition
  type      = var.type

  dynamic "record" {
    for_each = var.record
    content {
      data = record.value["data"]
      name = record.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.bigip_ltm_datagroup.this.id
}

output "type" {
  description = "returns a string"
  value       = data.bigip_ltm_datagroup.this.type
}

output "this" {
  value = bigip_ltm_datagroup.this
}
```

[top](#index)