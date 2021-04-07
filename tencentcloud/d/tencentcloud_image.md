# tencentcloud_image

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_image" {
  source = "./modules/tencentcloud/d/tencentcloud_image"

  # image_name_regex - (optional) is a type of string
  image_name_regex = null
  # os_name - (optional) is a type of string
  os_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "image_name_regex" {
  description = "(optional) - A regex string to apply to the image list returned by TencentCloud. **NOTE**: it is not wildcard, should look like `image_name_regex = \"^CentOS\\s+6\\.8\\s+64\\w*\"`."
  type        = string
  default     = null
}

variable "os_name" {
  description = "(optional) - A string to apply with fuzzy match to the os_name attribute on the image list returned by TencentCloud. **NOTE**: when os_name is provided, highest priority is applied in this field instead of `image_name_regex`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_image" "this" {
  image_name_regex   = var.image_name_regex
  os_name            = var.os_name
  result_output_file = var.result_output_file

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_image.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.tencentcloud_image.this.image_id
}

output "image_name" {
  description = "returns a string"
  value       = data.tencentcloud_image.this.image_name
}

output "this" {
  value = tencentcloud_image.this
}
```

[top](#index)