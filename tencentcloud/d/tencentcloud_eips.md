# tencentcloud_eips

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
module "tencentcloud_eips" {
  source = "./modules/tencentcloud/d/tencentcloud_eips"

  # eip_id - (optional) is a type of string
  eip_id = null
  # eip_name - (optional) is a type of string
  eip_name = null
  # public_ip - (optional) is a type of string
  public_ip = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "eip_id" {
  description = "(optional) - ID of the EIP to be queried."
  type        = string
  default     = null
}

variable "eip_name" {
  description = "(optional) - Name of the EIP to be queried."
  type        = string
  default     = null
}

variable "public_ip" {
  description = "(optional) - The elastic ip address."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags of EIP."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_eips" "this" {
  # eip_id - (optional) is a type of string
  eip_id = var.eip_id
  # eip_name - (optional) is a type of string
  eip_name = var.eip_name
  # public_ip - (optional) is a type of string
  public_ip = var.public_ip
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "eip_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_eips.this.eip_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_eips.this.id
}

output "this" {
  value = tencentcloud_eips.this
}
```

[top](#index)