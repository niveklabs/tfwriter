# akamai_networklist_network_lists

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
module "akamai_networklist_network_lists" {
  source = "./modules/akamai/d/akamai_networklist_network_lists"

  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_networklist_network_lists" "this" {
  name = var.name
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_networklist_network_lists.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_networklist_network_lists.this.json
}

output "list" {
  description = "returns a list of string"
  value       = data.akamai_networklist_network_lists.this.list
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_networklist_network_lists.this.output_text
}

output "uniqueid" {
  description = "returns a string"
  value       = data.akamai_networklist_network_lists.this.uniqueid
}

output "this" {
  value = akamai_networklist_network_lists.this
}
```

[top](#index)