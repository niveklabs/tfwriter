# oci_analytics_analytics_instance_vanity_url

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_analytics_analytics_instance_vanity_url" {
  source = "./modules/oci/r/oci_analytics_analytics_instance_vanity_url"

  # analytics_instance_id - (required) is a type of string
  analytics_instance_id = null
  # ca_certificate - (required) is a type of string
  ca_certificate = null
  # description - (optional) is a type of string
  description = null
  # hosts - (required) is a type of list of string
  hosts = []
  # passphrase - (optional) is a type of string
  passphrase = null
  # private_key - (required) is a type of string
  private_key = null
  # public_certificate - (required) is a type of string
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
variable "analytics_instance_id" {
  description = "(required)"
  type        = string
}

variable "ca_certificate" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hosts" {
  description = "(required)"
  type        = list(string)
}

variable "passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "public_certificate" {
  description = "(required)"
  type        = string
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
resource "oci_analytics_analytics_instance_vanity_url" "this" {
  analytics_instance_id = var.analytics_instance_id
  ca_certificate        = var.ca_certificate
  description           = var.description
  hosts                 = var.hosts
  passphrase            = var.passphrase
  private_key           = var.private_key
  public_certificate    = var.public_certificate

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
output "id" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance_vanity_url.this.id
}

output "this" {
  value = oci_analytics_analytics_instance_vanity_url.this
}
```

[top](#index)