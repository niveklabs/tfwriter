# alicloud_file_crc64_checksum

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_file_crc64_checksum" {
  source = "./modules/alicloud/d/alicloud_file_crc64_checksum"

  # filename - (required) is a type of string
  filename = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "filename" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_file_crc64_checksum" "this" {
  filename    = var.filename
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "checksum" {
  description = "returns a string"
  value       = data.alicloud_file_crc64_checksum.this.checksum
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_file_crc64_checksum.this.id
}

output "this" {
  value = alicloud_file_crc64_checksum.this
}
```

[top](#index)