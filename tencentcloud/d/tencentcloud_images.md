# tencentcloud_images

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
module "tencentcloud_images" {
  source = "./modules/tencentcloud/d/tencentcloud_images"

  # image_id - (optional) is a type of string
  image_id = null
  # image_name_regex - (optional) is a type of string
  image_name_regex = null
  # image_type - (optional) is a type of list of string
  image_type = []
  # os_name - (optional) is a type of string
  os_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(optional) - ID of the image to be queried."
  type        = string
  default     = null
}

variable "image_name_regex" {
  description = "(optional) - A regex string to apply to the image list returned by TencentCloud, conflict with 'os_name'. **NOTE**: it is not wildcard, should look like `image_name_regex = \"^CentOS\\s+6\\.8\\s+64\\w*\"`."
  type        = string
  default     = null
}

variable "image_type" {
  description = "(optional) - A list of the image type to be queried. Valid values: 'PUBLIC_IMAGE', 'PRIVATE_IMAGE', 'SHARED_IMAGE', 'MARKET_IMAGE'."
  type        = list(string)
  default     = null
}

variable "os_name" {
  description = "(optional) - A string to apply with fuzzy match to the os_name attribute on the image list returned by TencentCloud, conflict with 'image_name_regex'."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_images" "this" {
  image_id           = var.image_id
  image_name_regex   = var.image_name_regex
  image_type         = var.image_type
  os_name            = var.os_name
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_images.this.id
}

output "images" {
  description = "returns a list of object"
  value       = data.tencentcloud_images.this.images
}

output "this" {
  value = tencentcloud_images.this
}
```

[top](#index)