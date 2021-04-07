# tencentcloud_cam_saml_providers

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
module "tencentcloud_cam_saml_providers" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_saml_providers"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The description of the CAM SAML provider."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the CAM SAML provider to be queried."
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
data "tencentcloud_cam_saml_providers" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_saml_providers.this.id
}

output "provider_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_saml_providers.this.provider_list
}

output "this" {
  value = tencentcloud_cam_saml_providers.this
}
```

[top](#index)