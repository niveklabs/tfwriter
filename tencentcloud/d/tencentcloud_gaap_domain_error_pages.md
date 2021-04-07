# tencentcloud_gaap_domain_error_pages

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
module "tencentcloud_gaap_domain_error_pages" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_domain_error_pages"

  # domain - (required) is a type of string
  domain = null
  # ids - (optional) is a type of set of string
  ids = []
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
  description = "(required) - HTTP domain to be queried."
  type        = string
}

variable "ids" {
  description = "(optional) - List of the error page info ID to be queried."
  type        = set(string)
  default     = null
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
data "tencentcloud_gaap_domain_error_pages" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # ids - (optional) is a type of set of string
  ids = var.ids
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "error_page_info_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_domain_error_pages.this.error_page_info_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_domain_error_pages.this.id
}

output "this" {
  value = tencentcloud_gaap_domain_error_pages.this
}
```

[top](#index)