# thunder_slb_http2

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
module "thunder_slb_http2" {
  source = "./modules/thunder/r/thunder_slb_http2"

  # uuid - (optional) is a type of string
  uuid = null

  sampling_enable = [{
    counters1 = null
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

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_http2" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      # counters1 - (optional) is a type of string
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_http2.this.id
}

output "this" {
  value = thunder_slb_http2.this
}
```

[top](#index)