# akamai_property_variables

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property_variables" {
  source = "./modules/akamai/r/akamai_property_variables"


  variables = [{
    variable = [{
      description = null
      hidden      = null
      name        = null
      sensitive   = null
      value       = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "variables" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      variable = set(object(
        {
          description = string
          hidden      = bool
          name        = string
          sensitive   = bool
          value       = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_property_variables" "this" {

  dynamic "variables" {
    for_each = var.variables
    content {

      dynamic "variable" {
        for_each = variables.value.variable
        content {
          description = variable.value["description"]
          hidden      = variable.value["hidden"]
          name        = variable.value["name"]
          sensitive   = variable.value["sensitive"]
          value       = variable.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_property_variables.this.id
}

output "json" {
  description = "returns a string"
  value       = akamai_property_variables.this.json
}

output "this" {
  value = akamai_property_variables.this
}
```

[top](#index)