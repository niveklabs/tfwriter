# alicloud_cdn_domain_config

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cdn_domain_config" {
  source = "./modules/alicloud/r/alicloud_cdn_domain_config"

  # domain_name - (required) is a type of string
  domain_name = null
  # function_name - (required) is a type of string
  function_name = null

  function_args = [{
    arg_name  = null
    arg_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "function_name" {
  description = "(required)"
  type        = string
}

variable "function_args" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      arg_name  = string
      arg_value = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cdn_domain_config" "this" {
  domain_name   = var.domain_name
  function_name = var.function_name

  dynamic "function_args" {
    for_each = var.function_args
    content {
      arg_name  = function_args.value["arg_name"]
      arg_value = function_args.value["arg_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cdn_domain_config.this.id
}

output "this" {
  value = alicloud_cdn_domain_config.this
}
```

[top](#index)