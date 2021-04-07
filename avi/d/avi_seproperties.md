# avi_seproperties

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_seproperties" {
  source = "./modules/avi/d/avi_seproperties"

  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_seproperties" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.avi_seproperties.this.id
}

output "se_agent_properties" {
  description = "returns a set of object"
  value       = data.avi_seproperties.this.se_agent_properties
}

output "se_bootup_properties" {
  description = "returns a set of object"
  value       = data.avi_seproperties.this.se_bootup_properties
}

output "se_runtime_properties" {
  description = "returns a set of object"
  value       = data.avi_seproperties.this.se_runtime_properties
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_seproperties.this.uuid
}

output "this" {
  value = avi_seproperties.this
}
```

[top](#index)