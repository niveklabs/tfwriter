# alicloud_logtail_attachment

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_logtail_attachment" {
  source = "./modules/alicloud/r/alicloud_logtail_attachment"

  # logtail_config_name - (required) is a type of string
  logtail_config_name = null
  # machine_group_name - (required) is a type of string
  machine_group_name = null
  # project - (required) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "logtail_config_name" {
  description = "(required)"
  type        = string
}

variable "machine_group_name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_logtail_attachment" "this" {
  logtail_config_name = var.logtail_config_name
  machine_group_name  = var.machine_group_name
  project             = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_logtail_attachment.this.id
}

output "this" {
  value = alicloud_logtail_attachment.this
}
```

[top](#index)