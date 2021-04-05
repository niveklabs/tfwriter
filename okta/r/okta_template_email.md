# okta_template_email

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_template_email" {
  source = "./modules/okta/r/okta_template_email"

  # default_language - (optional) is a type of string
  default_language = null
  # type - (required) is a type of string
  type = null

  translations = [{
    language = null
    subject  = null
    template = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Email template type"
  type        = string
}

variable "translations" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      language = string
      subject  = string
      template = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "okta_template_email" "this" {
  default_language = var.default_language
  type             = var.type

  dynamic "translations" {
    for_each = var.translations
    content {
      language = translations.value["language"]
      subject  = translations.value["subject"]
      template = translations.value["template"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_template_email.this.id
}

output "this" {
  value = okta_template_email.this
}
```

[top](#index)