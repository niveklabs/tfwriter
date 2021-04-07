# tencentcloud_gaap_http_domains

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
module "tencentcloud_gaap_http_domains" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_http_domains"

  # domain - (required) is a type of string
  domain = null
  # listener_id - (required) is a type of string
  listener_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - Forward domain of the layer7 listener to be queried."
  type        = string
}

variable "listener_id" {
  description = "(required) - ID of the layer7 listener to be queried."
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
data "tencentcloud_gaap_http_domains" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_http_domains.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_http_domains.this.id
}

output "this" {
  value = tencentcloud_gaap_http_domains.this
}
```

[top](#index)