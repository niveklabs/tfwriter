# tencentcloud_cbs_storage_attachment

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
module "tencentcloud_cbs_storage_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_cbs_storage_attachment"

  # instance_id - (required) is a type of string
  instance_id = null
  # storage_id - (required) is a type of string
  storage_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - ID of the CVM instance."
  type        = string
}

variable "storage_id" {
  description = "(required) - ID of the mounted CBS."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cbs_storage_attachment" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # storage_id - (required) is a type of string
  storage_id = var.storage_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cbs_storage_attachment.this.id
}

output "this" {
  value = tencentcloud_cbs_storage_attachment.this
}
```

[top](#index)