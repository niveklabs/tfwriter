# thunder_ip_tcp

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_ip_tcp" {
  source = "./modules/thunder/r/thunder_ip_tcp"

  # uuid - (optional) is a type of string
  uuid = null

  syn_cookie = [{
    threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syn_cookie" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      threshold = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_ip_tcp" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "syn_cookie" {
    for_each = var.syn_cookie
    content {
      # threshold - (optional) is a type of number
      threshold = syn_cookie.value["threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_tcp.this.id
}

output "this" {
  value = thunder_ip_tcp.this
}
```

[top](#index)