# tencentcloud_dc_gateway_ccn_route

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
module "tencentcloud_dc_gateway_ccn_route" {
  source = "./modules/tencentcloud/r/tencentcloud_dc_gateway_ccn_route"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # dcg_id - (required) is a type of string
  dcg_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required) - A network address segment of IDC."
  type        = string
}

variable "dcg_id" {
  description = "(required) - ID of the DCG."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dc_gateway_ccn_route" "this" {
  cidr_block = var.cidr_block
  dcg_id     = var.dcg_id
}
```

[top](#index)

### Outputs

```terraform
output "as_path" {
  description = "returns a list of string"
  value       = tencentcloud_dc_gateway_ccn_route.this.as_path
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dc_gateway_ccn_route.this.id
}

output "this" {
  value = tencentcloud_dc_gateway_ccn_route.this
}
```

[top](#index)