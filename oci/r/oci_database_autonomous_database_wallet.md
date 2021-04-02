# oci_database_autonomous_database_wallet

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_database_wallet" {
  source = "./modules/oci/r/oci_database_autonomous_database_wallet"

  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = null
  # base64_encode_content - (optional) is a type of bool
  base64_encode_content = null
  # generate_type - (optional) is a type of string
  generate_type = null
  # password - (required) is a type of string
  password = null

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
variable "autonomous_database_id" {
  description = "(required)"
  type        = string
}

variable "base64_encode_content" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "generate_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
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
resource "oci_database_autonomous_database_wallet" "this" {
  autonomous_database_id = var.autonomous_database_id
  base64_encode_content  = var.base64_encode_content
  generate_type          = var.generate_type
  password               = var.password

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
output "content" {
  description = "returns a string"
  value       = oci_database_autonomous_database_wallet.this.content
}

output "id" {
  description = "returns a string"
  value       = oci_database_autonomous_database_wallet.this.id
}

output "this" {
  value = oci_database_autonomous_database_wallet.this
}
```

[top](#index)