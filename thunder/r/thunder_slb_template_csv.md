# thunder_slb_template_csv

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
module "thunder_slb_template_csv" {
  source = "./modules/thunder/r/thunder_slb_template_csv"

  # csv_name - (optional) is a type of string
  csv_name = null
  # delim_char - (optional) is a type of string
  delim_char = null
  # delim_num - (optional) is a type of number
  delim_num = null
  # ipv6_enable - (optional) is a type of number
  ipv6_enable = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  multiple_fields = [{
    csv_type = null
    field    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "csv_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delim_char" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delim_num" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multiple_fields" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      csv_type = string
      field    = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_csv" "this" {
  csv_name    = var.csv_name
  delim_char  = var.delim_char
  delim_num   = var.delim_num
  ipv6_enable = var.ipv6_enable
  user_tag    = var.user_tag
  uuid        = var.uuid

  dynamic "multiple_fields" {
    for_each = var.multiple_fields
    content {
      csv_type = multiple_fields.value["csv_type"]
      field    = multiple_fields.value["field"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_csv.this.id
}

output "this" {
  value = thunder_slb_template_csv.this
}
```

[top](#index)