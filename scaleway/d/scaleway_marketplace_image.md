# scaleway_marketplace_image

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_marketplace_image" {
  source = "./modules/scaleway/d/scaleway_marketplace_image"

  # instance_type - (optional) is a type of string
  instance_type = null
  # label - (required) is a type of string
  label = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_type" {
  description = "(optional) - The instance commercial type of the desired image"
  type        = string
  default     = null
}

variable "label" {
  description = "(required) - Exact label of the desired image"
  type        = string
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_marketplace_image" "this" {
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # label - (required) is a type of string
  label = var.label
  # zone - (optional) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.scaleway_marketplace_image.this.id
}

output "zone" {
  description = "returns a string"
  value       = data.scaleway_marketplace_image.this.zone
}

output "this" {
  value = scaleway_marketplace_image.this
}
```

[top](#index)