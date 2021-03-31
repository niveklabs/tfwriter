# aviatrix_saml_endpoint

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_saml_endpoint" {
  source = "./modules/aviatrix/r/aviatrix_saml_endpoint"

  # access_set_by - (optional) is a type of string
  access_set_by = null
  # controller_login - (optional) is a type of bool
  controller_login = null
  # custom_entity_id - (optional) is a type of string
  custom_entity_id = null
  # custom_saml_request_template - (optional) is a type of string
  custom_saml_request_template = null
  # endpoint_name - (required) is a type of string
  endpoint_name = null
  # idp_metadata - (optional) is a type of string
  idp_metadata = null
  # idp_metadata_type - (required) is a type of string
  idp_metadata_type = null
  # idp_metadata_url - (optional) is a type of string
  idp_metadata_url = null
  # rbac_groups - (optional) is a type of list of string
  rbac_groups = []
  # sign_authn_requests - (optional) is a type of bool
  sign_authn_requests = null
}
```

[top](#index)

### Variables

```terraform
variable "access_set_by" {
  description = "(optional) - Access type."
  type        = string
  default     = null
}

variable "controller_login" {
  description = "(optional) - Switch to differentiate if it is for controller login."
  type        = bool
  default     = null
}

variable "custom_entity_id" {
  description = "(optional) - Custom Entity ID. Required to be non-empty for 'Custom' Entity ID type, empty for 'Hostname'."
  type        = string
  default     = null
}

variable "custom_saml_request_template" {
  description = "(optional) - Custom SAML Request Template."
  type        = string
  default     = null
}

variable "endpoint_name" {
  description = "(required) - SAML Endpoint Name."
  type        = string
}

variable "idp_metadata" {
  description = "(optional) - IDP Metadata."
  type        = string
  default     = null
}

variable "idp_metadata_type" {
  description = "(required) - Type of IDP Metadata."
  type        = string
}

variable "idp_metadata_url" {
  description = "(optional) - IDP Metadata."
  type        = string
  default     = null
}

variable "rbac_groups" {
  description = "(optional) - List of RBAC groups."
  type        = list(string)
  default     = null
}

variable "sign_authn_requests" {
  description = "(optional) - Whether to sign SAML AuthnRequests"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_saml_endpoint" "this" {
  access_set_by                = var.access_set_by
  controller_login             = var.controller_login
  custom_entity_id             = var.custom_entity_id
  custom_saml_request_template = var.custom_saml_request_template
  endpoint_name                = var.endpoint_name
  idp_metadata                 = var.idp_metadata
  idp_metadata_type            = var.idp_metadata_type
  idp_metadata_url             = var.idp_metadata_url
  rbac_groups                  = var.rbac_groups
  sign_authn_requests          = var.sign_authn_requests
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_saml_endpoint.this.id
}

output "this" {
  value = aviatrix_saml_endpoint.this
}
```

[top](#index)