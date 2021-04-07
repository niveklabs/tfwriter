# tencentcloud_gaap_certificates

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
module "tencentcloud_gaap_certificates" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_certificates"

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
  description = "(optional) - Name of the certificate to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of the certificate to be queried. Valid values: `BASIC`, `CLIENT`, `SERVER`, `REALSERVER` and `PROXY`. `BASIC` means basic certificate; `CLIENT` means client CA certificate; `SERVER` means server SSL certificate; `REALSERVER` means realserver CA certificate; `PROXY` means proxy SSL certificate."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_gaap_certificates" "this" {
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "certificates" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_certificates.this.certificates
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_certificates.this.id
}

output "this" {
  value = tencentcloud_gaap_certificates.this
}
```

[top](#index)