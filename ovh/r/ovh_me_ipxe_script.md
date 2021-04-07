# ovh_me_ipxe_script

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_ipxe_script" {
  source = "./modules/ovh/r/ovh_me_ipxe_script"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # script - (required) is a type of string
  script = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - For documentation purpose only. This attribute is not passed to the OVH API as it cannot be retrieved back. Instead a fake description ('$name auto description') is passed at creation time."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of your script"
  type        = string
}

variable "script" {
  description = "(required) - Content of your IPXE script"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_ipxe_script" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # script - (required) is a type of string
  script = var.script
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = ovh_me_ipxe_script.this.description
}

output "id" {
  description = "returns a string"
  value       = ovh_me_ipxe_script.this.id
}

output "this" {
  value = ovh_me_ipxe_script.this
}
```

[top](#index)