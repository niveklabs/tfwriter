# scaleway_lb_certificate

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "scaleway_lb_certificate" {
  source = "./modules/scaleway/r/scaleway_lb_certificate"

  # lb_id - (required) is a type of string
  lb_id = null
  # name - (optional) is a type of string
  name = null

  custom_certificate = [{
    certificate_chain = null
  }]

  letsencrypt = [{
    common_name              = null
    subject_alternative_name = []
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "lb_id" {
  description = "(required) - The load-balancer ID"
  type        = string
}

variable "name" {
  description = "(optional) - The name of the load-balancer certificate"
  type        = string
  default     = null
}

variable "custom_certificate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_chain = string
    }
  ))
  default = []
}

variable "letsencrypt" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      common_name              = string
      subject_alternative_name = list(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_lb_certificate" "this" {
  # lb_id - (required) is a type of string
  lb_id = var.lb_id
  # name - (optional) is a type of string
  name = var.name

  dynamic "custom_certificate" {
    for_each = var.custom_certificate
    content {
      # certificate_chain - (required) is a type of string
      certificate_chain = custom_certificate.value["certificate_chain"]
    }
  }

  dynamic "letsencrypt" {
    for_each = var.letsencrypt
    content {
      # common_name - (required) is a type of string
      common_name = letsencrypt.value["common_name"]
      # subject_alternative_name - (optional) is a type of list of string
      subject_alternative_name = letsencrypt.value["subject_alternative_name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "common_name" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.common_name
}

output "fingerprint" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.name
}

output "not_valid_after" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.not_valid_after
}

output "not_valid_before" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.not_valid_before
}

output "status" {
  description = "returns a string"
  value       = scaleway_lb_certificate.this.status
}

output "subject_alternative_name" {
  description = "returns a list of string"
  value       = scaleway_lb_certificate.this.subject_alternative_name
}

output "this" {
  value = scaleway_lb_certificate.this
}
```

[top](#index)