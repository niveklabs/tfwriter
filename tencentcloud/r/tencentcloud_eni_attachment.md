# tencentcloud_eni_attachment

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_eni_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_eni_attachment"

  # eni_id - (required) is a type of string
  eni_id = null
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "eni_id" {
  description = "(required) - ID of the ENI."
  type        = string
}

variable "instance_id" {
  description = "(required) - ID of the instance which bind the ENI."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_eni_attachment" "this" {
  # eni_id - (required) is a type of string
  eni_id = var.eni_id
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_eni_attachment.this.id
}

output "this" {
  value = tencentcloud_eni_attachment.this
}
```

[top](#index)