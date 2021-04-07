# tencentcloud_dc_gateway_ccn_routes

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
module "tencentcloud_dc_gateway_ccn_routes" {
  source = "./modules/tencentcloud/d/tencentcloud_dc_gateway_ccn_routes"

  # dcg_id - (required) is a type of string
  dcg_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "dcg_id" {
  description = "(required) - ID of the DCG to be queried."
  type        = string
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
data "tencentcloud_dc_gateway_ccn_routes" "this" {
  dcg_id             = var.dcg_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dc_gateway_ccn_routes.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dc_gateway_ccn_routes.this.instance_list
}

output "this" {
  value = tencentcloud_dc_gateway_ccn_routes.this
}
```

[top](#index)