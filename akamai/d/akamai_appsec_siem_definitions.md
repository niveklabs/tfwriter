# akamai_appsec_siem_definitions

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "akamai_appsec_siem_definitions" {
  source = "./modules/akamai/d/akamai_appsec_siem_definitions"

  # siem_definition_name - (optional) is a type of string
  siem_definition_name = null
}
```

[top](#index)

### Variables

```terraform
variable "siem_definition_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_siem_definitions" "this" {
  # siem_definition_name - (optional) is a type of string
  siem_definition_name = var.siem_definition_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_siem_definitions.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_siem_definitions.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_siem_definitions.this.output_text
}

output "this" {
  value = akamai_appsec_siem_definitions.this
}
```

[top](#index)