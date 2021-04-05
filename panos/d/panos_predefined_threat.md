# panos_predefined_threat

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_predefined_threat" {
  source = "./modules/panos/d/panos_predefined_threat"

  # name - (optional) is a type of string
  name = null
  # threat_name - (optional) is a type of string
  threat_name = null
  # threat_regex - (optional) is a type of string
  threat_regex = null
  # threat_type - (optional) is a type of string
  threat_type = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - A specific threat ID / name"
  type        = string
  default     = null
}

variable "threat_name" {
  description = "(optional) - An exact match against the threat name"
  type        = string
  default     = null
}

variable "threat_regex" {
  description = "(optional) - A regex to apply to the threat name"
  type        = string
  default     = null
}

variable "threat_type" {
  description = "(optional) - The threat type"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "panos_predefined_threat" "this" {
  name         = var.name
  threat_name  = var.threat_name
  threat_regex = var.threat_regex
  threat_type  = var.threat_type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.panos_predefined_threat.this.id
}

output "threats" {
  description = "returns a list of object"
  value       = data.panos_predefined_threat.this.threats
}

output "total" {
  description = "returns a number"
  value       = data.panos_predefined_threat.this.total
}

output "this" {
  value = panos_predefined_threat.this
}
```

[top](#index)