# cloudflare_api_token

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
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_api_token" {
  source = "./modules/cloudflare/r/cloudflare_api_token"

  # name - (required) is a type of string
  name = null

  condition = [{
    request_ip = [{
      in     = []
      not_in = []
    }]
  }]

  policy = [{
    effect            = null
    permission_groups = []
    resources         = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      request_ip = list(object(
        {
          in     = list(string)
          not_in = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "policy" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      effect            = string
      permission_groups = list(string)
      resources         = map(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_api_token" "this" {
  name = var.name

  dynamic "condition" {
    for_each = var.condition
    content {

      dynamic "request_ip" {
        for_each = condition.value.request_ip
        content {
          in     = request_ip.value["in"]
          not_in = request_ip.value["not_in"]
        }
      }

    }
  }

  dynamic "policy" {
    for_each = var.policy
    content {
      effect            = policy.value["effect"]
      permission_groups = policy.value["permission_groups"]
      resources         = policy.value["resources"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_api_token.this.id
}

output "issued_on" {
  description = "returns a string"
  value       = cloudflare_api_token.this.issued_on
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_api_token.this.modified_on
}

output "status" {
  description = "returns a string"
  value       = cloudflare_api_token.this.status
}

output "value" {
  description = "returns a string"
  value       = cloudflare_api_token.this.value
  sensitive   = true
}

output "this" {
  value = cloudflare_api_token.this
}
```

[top](#index)