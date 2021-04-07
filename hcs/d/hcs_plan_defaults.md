# hcs_plan_defaults

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcs = ">= 0.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcs_plan_defaults" {
  source = "./modules/hcs/d/hcs_plan_defaults"


  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

### Datasource

```terraform
data "hcs_plan_defaults" "this" {

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
output "id" {
  description = "returns a string"
  value       = data.hcs_plan_defaults.this.id
}

output "offer" {
  description = "returns a string"
  value       = data.hcs_plan_defaults.this.offer
}

output "plan_name" {
  description = "returns a string"
  value       = data.hcs_plan_defaults.this.plan_name
}

output "plan_version" {
  description = "returns a string"
  value       = data.hcs_plan_defaults.this.plan_version
}

output "publisher" {
  description = "returns a string"
  value       = data.hcs_plan_defaults.this.publisher
}

output "this" {
  value = hcs_plan_defaults.this
}
```

[top](#index)