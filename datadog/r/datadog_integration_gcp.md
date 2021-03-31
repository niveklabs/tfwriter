# datadog_integration_gcp

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_gcp" {
  source = "./modules/datadog/r/datadog_integration_gcp"

  # client_email - (required) is a type of string
  client_email = null
  # client_id - (required) is a type of string
  client_id = null
  # host_filters - (optional) is a type of string
  host_filters = null
  # private_key - (required) is a type of string
  private_key = null
  # private_key_id - (required) is a type of string
  private_key_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_email" {
  description = "(required) - Your email found in your JSON service account key."
  type        = string
}

variable "client_id" {
  description = "(required) - Your ID found in your JSON service account key."
  type        = string
}

variable "host_filters" {
  description = "(optional) - Limit the GCE instances that are pulled into Datadog by using tags. Only hosts that match one of the defined tags are imported into Datadog."
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required) - Your private key name found in your JSON service account key."
  type        = string
}

variable "private_key_id" {
  description = "(required) - Your private key ID found in your JSON service account key."
  type        = string
}

variable "project_id" {
  description = "(required) - Your Google Cloud project ID found in your JSON service account key."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_gcp" "this" {
  client_email   = var.client_email
  client_id      = var.client_id
  host_filters   = var.host_filters
  private_key    = var.private_key
  private_key_id = var.private_key_id
  project_id     = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_gcp.this.id
}

output "this" {
  value = datadog_integration_gcp.this
}
```

[top](#index)