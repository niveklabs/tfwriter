# google_iam_workload_identity_pool_provider

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_iam_workload_identity_pool_provider" {
  source = "./modules/google-beta/r/google_iam_workload_identity_pool_provider"

  # attribute_condition - (optional) is a type of string
  attribute_condition = null
  # attribute_mapping - (optional) is a type of map of string
  attribute_mapping = {}
  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # display_name - (optional) is a type of string
  display_name = null
  # project - (optional) is a type of string
  project = null
  # workload_identity_pool_id - (required) is a type of string
  workload_identity_pool_id = null
  # workload_identity_pool_provider_id - (required) is a type of string
  workload_identity_pool_provider_id = null

  aws = [{
    account_id = null
  }]

  oidc = [{
    allowed_audiences = []
    issuer_uri        = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "attribute_condition" {
  description = "(optional) - [A Common Expression Language](https://opensource.google/projects/cel) expression, in\nplain text, to restrict what otherwise valid authentication credentials issued by the\nprovider should not be accepted.\n\nThe expression must output a boolean representing whether to allow the federation.\n\nThe following keywords may be referenced in the expressions:\n  * 'assertion': JSON representing the authentication credential issued by the provider.\n  * 'google': The Google attributes mapped from the assertion in the 'attribute_mappings'.\n  * 'attribute': The custom attributes mapped from the assertion in the 'attribute_mappings'.\n\nThe maximum length of the attribute condition expression is 4096 characters. If\nunspecified, all valid authentication credential are accepted.\n\nThe following example shows how to only allow credentials with a mapped 'google.groups'\nvalue of 'admins':\n'''\n\"'admins' in google.groups\"\n'''"
  type        = string
  default     = null
}

variable "attribute_mapping" {
  description = "(optional) - Maps attributes from authentication credentials issued by an external identity provider\nto Google Cloud attributes, such as 'subject' and 'segment'.\n\nEach key must be a string specifying the Google Cloud IAM attribute to map to.\n\nThe following keys are supported:\n  * 'google.subject': The principal IAM is authenticating. You can reference this value\n    in IAM bindings. This is also the subject that appears in Cloud Logging logs.\n    Cannot exceed 127 characters.\n  * 'google.groups': Groups the external identity belongs to. You can grant groups\n    access to resources using an IAM 'principalSet' binding; access applies to all\n    members of the group.\n\nYou can also provide custom attributes by specifying 'attribute.{custom_attribute}',\nwhere '{custom_attribute}' is the name of the custom attribute to be mapped. You can\ndefine a maximum of 50 custom attributes. The maximum length of a mapped attribute key\nis 100 characters, and the key may only contain the characters [a-z0-9_].\n\nYou can reference these attributes in IAM policies to define fine-grained access for a\nworkload to Google Cloud resources. For example:\n  * 'google.subject':\n    'principal://iam.googleapis.com/projects/{project}/locations/{location}/workloadIdentityPools/{pool}/subject/{value}'\n  * 'google.groups':\n    'principalSet://iam.googleapis.com/projects/{project}/locations/{location}/workloadIdentityPools/{pool}/group/{value}'\n  * 'attribute.{custom_attribute}':\n    'principalSet://iam.googleapis.com/projects/{project}/locations/{location}/workloadIdentityPools/{pool}/attribute.{custom_attribute}/{value}'\n\nEach value must be a [Common Expression Language](https://opensource.google/projects/cel)\nfunction that maps an identity provider credential to the normalized attribute specified\nby the corresponding map key.\n\nYou can use the 'assertion' keyword in the expression to access a JSON representation of\nthe authentication credential issued by the provider.\n\nThe maximum length of an attribute mapping expression is 2048 characters. When evaluated,\nthe total size of all mapped attributes must not exceed 8KB.\n\nFor AWS providers, the following rules apply:\n  - If no attribute mapping is defined, the following default mapping applies:\n    '''\n    {\n      \"google.subject\":\"assertion.arn\",\n      \"attribute.aws_role\":\n        \"assertion.arn.contains('assumed-role')\"\n        \" ? assertion.arn.extract('{account_arn}assumed-role/')\"\n        \"   + 'assumed-role/'\"\n        \"   + assertion.arn.extract('assumed-role/{role_name}/')\"\n        \" : assertion.arn\",\n    }\n    '''\n  - If any custom attribute mappings are defined, they must include a mapping to the\n    'google.subject' attribute.\n\nFor OIDC providers, the following rules apply:\n  - Custom attribute mappings must be defined, and must include a mapping to the\n    'google.subject' attribute. For example, the following maps the 'sub' claim of the\n    incoming credential to the 'subject' attribute on a Google token.\n    '''\n    {\"google.subject\": \"assertion.sub\"}\n    '''"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - A description for the provider. Cannot exceed 256 characters."
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional) - Whether the provider is disabled. You cannot use a disabled provider to exchange tokens.\nHowever, existing tokens still grant access."
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional) - A display name for the provider. Cannot exceed 32 characters."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workload_identity_pool_id" {
  description = "(required) - The ID used for the pool, which is the final component of the pool resource name. This\nvalue should be 4-32 characters, and may contain the characters [a-z0-9-]. The prefix\n'gcp-' is reserved for use by Google, and may not be specified."
  type        = string
}

variable "workload_identity_pool_provider_id" {
  description = "(required) - The ID for the provider, which becomes the final component of the resource name. This\nvalue must be 4-32 characters, and may contain the characters [a-z0-9-]. The prefix\n'gcp-' is reserved for use by Google, and may not be specified."
  type        = string
}

variable "aws" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_id = string
    }
  ))
  default = []
}

variable "oidc" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_audiences = list(string)
      issuer_uri        = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_iam_workload_identity_pool_provider" "this" {
  attribute_condition                = var.attribute_condition
  attribute_mapping                  = var.attribute_mapping
  description                        = var.description
  disabled                           = var.disabled
  display_name                       = var.display_name
  project                            = var.project
  workload_identity_pool_id          = var.workload_identity_pool_id
  workload_identity_pool_provider_id = var.workload_identity_pool_provider_id

  dynamic "aws" {
    for_each = var.aws
    content {
      account_id = aws.value["account_id"]
    }
  }

  dynamic "oidc" {
    for_each = var.oidc
    content {
      allowed_audiences = oidc.value["allowed_audiences"]
      issuer_uri        = oidc.value["issuer_uri"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool_provider.this.id
}

output "name" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool_provider.this.name
}

output "project" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool_provider.this.project
}

output "state" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool_provider.this.state
}

output "this" {
  value = google_iam_workload_identity_pool_provider.this
}
```

[top](#index)