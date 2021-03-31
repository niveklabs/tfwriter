# aci_fabric_path_ep

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_fabric_path_ep" {
  source = "./modules/aci/d/aci_fabric_path_ep"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # node_id - (required) is a type of string
  node_id = null
  # pod_id - (required) is a type of string
  pod_id = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_id" {
  description = "(required)"
  type        = string
}

variable "pod_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_fabric_path_ep" "this" {
  annotation  = var.annotation
  description = var.description
  name        = var.name
  node_id     = var.node_id
  pod_id      = var.pod_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_fabric_path_ep.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_fabric_path_ep.this.id
}

output "this" {
  value = aci_fabric_path_ep.this
}
```

[top](#index)