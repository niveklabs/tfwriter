# oci_load_balancer_certificate

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_certificate" {
  source = "./modules/oci/r/oci_load_balancer_certificate"

  # ca_certificate - (optional) is a type of string
  ca_certificate = null
  # certificate_name - (required) is a type of string
  certificate_name = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # passphrase - (optional) is a type of string
  passphrase = null
  # private_key - (optional) is a type of string
  private_key = null
  # public_certificate - (optional) is a type of string
  public_certificate = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ca_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_name" {
  description = "(required)"
  type        = string
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_load_balancer_certificate" "this" {
  ca_certificate     = var.ca_certificate
  certificate_name   = var.certificate_name
  load_balancer_id   = var.load_balancer_id
  passphrase         = var.passphrase
  private_key        = var.private_key
  public_certificate = var.public_certificate

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ca_certificate" {
  description = "returns a string"
  value       = oci_load_balancer_certificate.this.ca_certificate
}

output "id" {
  description = "returns a string"
  value       = oci_load_balancer_certificate.this.id
}

output "private_key" {
  description = "returns a string"
  value       = oci_load_balancer_certificate.this.private_key
  sensitive   = true
}

output "public_certificate" {
  description = "returns a string"
  value       = oci_load_balancer_certificate.this.public_certificate
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_certificate.this.state
}

output "this" {
  value = oci_load_balancer_certificate.this
}
```

[top](#index)