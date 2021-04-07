# akamai_appsec_version_notes

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
module "akamai_appsec_version_notes" {
  source = "./modules/akamai/r/akamai_appsec_version_notes"

  # config_id - (required) is a type of number
  config_id = null
  # version - (required) is a type of number
  version = null
  # version_notes - (required) is a type of string
  version_notes = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "version" {
  description = "(required)"
  type        = number
}

variable "version_notes" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_version_notes" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # version - (required) is a type of number
  version = var.version
  # version_notes - (required) is a type of string
  version_notes = var.version_notes
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_version_notes.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_version_notes.this.output_text
}

output "this" {
  value = akamai_appsec_version_notes.this
}
```

[top](#index)