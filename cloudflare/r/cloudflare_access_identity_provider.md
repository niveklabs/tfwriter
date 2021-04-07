# cloudflare_access_identity_provider

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_access_identity_provider" {
  source = "./modules/cloudflare/r/cloudflare_access_identity_provider"

  # account_id - (optional) is a type of string
  account_id = null
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
  # zone_id - (optional) is a type of string
  zone_id = null

  config = [{
    apps_domain          = null
    attributes           = []
    auth_url             = null
    centrify_account     = null
    centrify_app_id      = null
    certs_url            = null
    client_id            = null
    client_secret        = null
    directory_id         = null
    email_attribute_name = null
    idp_public_cert      = null
    issuer_url           = null
    okta_account         = null
    onelogin_account     = null
    redirect_url         = null
    sign_request         = null
    sso_target_url       = null
    support_groups       = null
    token_url            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      apps_domain          = string
      attributes           = list(string)
      auth_url             = string
      centrify_account     = string
      centrify_app_id      = string
      certs_url            = string
      client_id            = string
      client_secret        = string
      directory_id         = string
      email_attribute_name = string
      idp_public_cert      = string
      issuer_url           = string
      okta_account         = string
      onelogin_account     = string
      redirect_url         = string
      sign_request         = bool
      sso_target_url       = string
      support_groups       = bool
      token_url            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_access_identity_provider" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # name - (required) is a type of string
  name = var.name
  # type - (required) is a type of string
  type = var.type
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "config" {
    for_each = var.config
    content {
      # apps_domain - (optional) is a type of string
      apps_domain = config.value["apps_domain"]
      # attributes - (optional) is a type of list of string
      attributes = config.value["attributes"]
      # auth_url - (optional) is a type of string
      auth_url = config.value["auth_url"]
      # centrify_account - (optional) is a type of string
      centrify_account = config.value["centrify_account"]
      # centrify_app_id - (optional) is a type of string
      centrify_app_id = config.value["centrify_app_id"]
      # certs_url - (optional) is a type of string
      certs_url = config.value["certs_url"]
      # client_id - (optional) is a type of string
      client_id = config.value["client_id"]
      # client_secret - (optional) is a type of string
      client_secret = config.value["client_secret"]
      # directory_id - (optional) is a type of string
      directory_id = config.value["directory_id"]
      # email_attribute_name - (optional) is a type of string
      email_attribute_name = config.value["email_attribute_name"]
      # idp_public_cert - (optional) is a type of string
      idp_public_cert = config.value["idp_public_cert"]
      # issuer_url - (optional) is a type of string
      issuer_url = config.value["issuer_url"]
      # okta_account - (optional) is a type of string
      okta_account = config.value["okta_account"]
      # onelogin_account - (optional) is a type of string
      onelogin_account = config.value["onelogin_account"]
      # redirect_url - (optional) is a type of string
      redirect_url = config.value["redirect_url"]
      # sign_request - (optional) is a type of bool
      sign_request = config.value["sign_request"]
      # sso_target_url - (optional) is a type of string
      sso_target_url = config.value["sso_target_url"]
      # support_groups - (optional) is a type of bool
      support_groups = config.value["support_groups"]
      # token_url - (optional) is a type of string
      token_url = config.value["token_url"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_access_identity_provider.this.id
}

output "this" {
  value = cloudflare_access_identity_provider.this
}
```

[top](#index)