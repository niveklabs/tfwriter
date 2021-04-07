# tencentcloud_ssm_secret_versions

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
module "tencentcloud_ssm_secret_versions" {
  source = "./modules/tencentcloud/d/tencentcloud_ssm_secret_versions"

  # result_output_file - (optional) is a type of string
  result_output_file = null
  # secret_name - (required) is a type of string
  secret_name = null
  # version_id - (optional) is a type of string
  version_id = null
}
```

[top](#index)

### Variables

```terraform
variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "secret_name" {
  description = "(required) - Secret name used to filter result."
  type        = string
}

variable "version_id" {
  description = "(optional) - VersionId used to filter result."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_ssm_secret_versions" "this" {
  result_output_file = var.result_output_file
  secret_name        = var.secret_name
  version_id         = var.version_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ssm_secret_versions.this.id
}

output "secret_version_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ssm_secret_versions.this.secret_version_list
}

output "this" {
  value = tencentcloud_ssm_secret_versions.this
}
```

[top](#index)