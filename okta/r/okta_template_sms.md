# okta_template_sms

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
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_template_sms" {
  source = "./modules/okta/r/okta_template_sms"

  # template - (required) is a type of string
  template = null
  # type - (required) is a type of string
  type = null

  translations = [{
    language = null
    template = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "template" {
  description = "(required) - SMS default template"
  type        = string
}

variable "type" {
  description = "(required) - SMS template type"
  type        = string
}

variable "translations" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      language = string
      template = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_template_sms" "this" {
  template = var.template
  type     = var.type

  dynamic "translations" {
    for_each = var.translations
    content {
      language = translations.value["language"]
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
  value       = okta_template_sms.this.id
}

output "this" {
  value = okta_template_sms.this
}
```

[top](#index)