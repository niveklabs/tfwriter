# cloudflare_worker_script

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_worker_script" {
  source = "./modules/cloudflare/r/cloudflare_worker_script"

  # content - (required) is a type of string
  content = null
  # name - (required) is a type of string
  name = null

  kv_namespace_binding = [{
    name         = null
    namespace_id = null
  }]

  plain_text_binding = [{
    name = null
    text = null
  }]

  secret_text_binding = [{
    name = null
    text = null
  }]

  webassembly_binding = [{
    module = null
    name   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "kv_namespace_binding" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name         = string
      namespace_id = string
    }
  ))
  default = []
}

variable "plain_text_binding" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      text = string
    }
  ))
  default = []
}

variable "secret_text_binding" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      text = string
    }
  ))
  default = []
}

variable "webassembly_binding" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      module = string
      name   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_worker_script" "this" {
  content = var.content
  name    = var.name

  dynamic "kv_namespace_binding" {
    for_each = var.kv_namespace_binding
    content {
      name         = kv_namespace_binding.value["name"]
      namespace_id = kv_namespace_binding.value["namespace_id"]
    }
  }

  dynamic "plain_text_binding" {
    for_each = var.plain_text_binding
    content {
      name = plain_text_binding.value["name"]
      text = plain_text_binding.value["text"]
    }
  }

  dynamic "secret_text_binding" {
    for_each = var.secret_text_binding
    content {
      name = secret_text_binding.value["name"]
      text = secret_text_binding.value["text"]
    }
  }

  dynamic "webassembly_binding" {
    for_each = var.webassembly_binding
    content {
      module = webassembly_binding.value["module"]
      name   = webassembly_binding.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_worker_script.this.id
}

output "this" {
  value = cloudflare_worker_script.this
}
```

[top](#index)