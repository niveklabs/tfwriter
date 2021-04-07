# ad_computer

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_computer" {
  source = "./modules/ad/r/ad_computer"

  # container - (optional) is a type of string
  container = null
  # name - (required) is a type of string
  name = null
  # pre2kname - (optional) is a type of string
  pre2kname = null
}
```

[top](#index)

### Variables

```terraform
variable "container" {
  description = "(optional) - The DN of the container used to hold the computer account."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name for the computer account."
  type        = string
}

variable "pre2kname" {
  description = "(optional) - The pre-win2k name for the computer account."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ad_computer" "this" {
  # container - (optional) is a type of string
  container = var.container
  # name - (required) is a type of string
  name = var.name
  # pre2kname - (optional) is a type of string
  pre2kname = var.pre2kname
}
```

[top](#index)

### Outputs

```terraform
output "container" {
  description = "returns a string"
  value       = ad_computer.this.container
}

output "dn" {
  description = "returns a string"
  value       = ad_computer.this.dn
}

output "guid" {
  description = "returns a string"
  value       = ad_computer.this.guid
}

output "id" {
  description = "returns a string"
  value       = ad_computer.this.id
}

output "pre2kname" {
  description = "returns a string"
  value       = ad_computer.this.pre2kname
}

output "this" {
  value = ad_computer.this
}
```

[top](#index)