# acme_registration

[back](../acme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    acme = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "acme_registration" {
  source = "./modules/acme/r/acme_registration"

  # account_key_pem - (required) is a type of string
  account_key_pem = null
  # email_address - (required) is a type of string
  email_address = null

  external_account_binding = [{
    hmac_base64 = null
    key_id      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_key_pem" {
  description = "(required)"
  type        = string
}

variable "email_address" {
  description = "(required)"
  type        = string
}

variable "external_account_binding" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      hmac_base64 = string
      key_id      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "acme_registration" "this" {
  account_key_pem = var.account_key_pem
  email_address   = var.email_address

  dynamic "external_account_binding" {
    for_each = var.external_account_binding
    content {
      hmac_base64 = external_account_binding.value["hmac_base64"]
      key_id      = external_account_binding.value["key_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = acme_registration.this.id
}

output "registration_url" {
  description = "returns a string"
  value       = acme_registration.this.registration_url
}

output "this" {
  value = acme_registration.this
}
```

[top](#index)