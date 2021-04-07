# tencentcloud_ssl_certificates

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
module "tencentcloud_ssl_certificates" {
  source = "./modules/tencentcloud/d/tencentcloud_ssl_certificates"

  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the SSL certificate to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of the SSL certificate to be queried. Available values includes: `CA` and `SVR`."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_ssl_certificates" "this" {
  name               = var.name
  result_output_file = var.result_output_file
  type               = var.type
}
```

[top](#index)

### Outputs

```terraform
output "certificates" {
  description = "returns a list of object"
  value       = data.tencentcloud_ssl_certificates.this.certificates
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ssl_certificates.this.id
}

output "this" {
  value = tencentcloud_ssl_certificates.this
}
```

[top](#index)