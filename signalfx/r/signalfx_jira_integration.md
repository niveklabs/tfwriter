# signalfx_jira_integration

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_jira_integration" {
  source = "./modules/signalfx/r/signalfx_jira_integration"

  # api_token - (optional) is a type of string
  api_token = null
  # assignee_display_name - (optional) is a type of string
  assignee_display_name = null
  # assignee_name - (required) is a type of string
  assignee_name = null
  # auth_method - (required) is a type of string
  auth_method = null
  # base_url - (required) is a type of string
  base_url = null
  # enabled - (required) is a type of bool
  enabled = null
  # issue_type - (required) is a type of string
  issue_type = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # project_key - (required) is a type of string
  project_key = null
  # user_email - (optional) is a type of string
  user_email = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "api_token" {
  description = "(optional) - The API token for the user email"
  type        = string
  default     = null
}

variable "assignee_display_name" {
  description = "(optional) - Jira display name for the assignee"
  type        = string
  default     = null
}

variable "assignee_name" {
  description = "(required) - Jira user name for the assignee"
  type        = string
}

variable "auth_method" {
  description = "(required) - Authentication method used when creating the Jira integration. One of `EmailAndToken` or `UsernameAndPassword`"
  type        = string
}

variable "base_url" {
  description = "(required) - Base URL of the Jira instance that's integrated with SignalFx."
  type        = string
}

variable "enabled" {
  description = "(required) - Whether the integration is enabled or not"
  type        = bool
}

variable "issue_type" {
  description = "(required) - Issue type (for example, Story) for tickets that Jira creates for detector notifications. SignalFx validates issue types, so you must specify a type that's valid for the Jira project specified in `projectKey`."
  type        = string
}

variable "name" {
  description = "(required) - Name of the integration"
  type        = string
}

variable "password" {
  description = "(optional) - Password used to authenticate the Jira integration."
  type        = string
  default     = null
}

variable "project_key" {
  description = "(required) - Jira key of an existing project. When Jira creates a new ticket for a detector notification, the ticket is assigned to this project."
  type        = string
}

variable "user_email" {
  description = "(optional) - Email address used to authenticate the Jira integration."
  type        = string
  default     = null
}

variable "username" {
  description = "(optional) - User name used to authenticate the Jira integration."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_jira_integration" "this" {
  # api_token - (optional) is a type of string
  api_token = var.api_token
  # assignee_display_name - (optional) is a type of string
  assignee_display_name = var.assignee_display_name
  # assignee_name - (required) is a type of string
  assignee_name = var.assignee_name
  # auth_method - (required) is a type of string
  auth_method = var.auth_method
  # base_url - (required) is a type of string
  base_url = var.base_url
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # issue_type - (required) is a type of string
  issue_type = var.issue_type
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # project_key - (required) is a type of string
  project_key = var.project_key
  # user_email - (optional) is a type of string
  user_email = var.user_email
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_jira_integration.this.id
}

output "this" {
  value = signalfx_jira_integration.this
}
```

[top](#index)