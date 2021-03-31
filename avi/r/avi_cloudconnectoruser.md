# avi_cloudconnectoruser

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_cloudconnectoruser" {
  source = "./modules/avi/r/avi_cloudconnectoruser"

  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # private_key - (optional) is a type of string
  private_key = null
  # public_key - (optional) is a type of string
  public_key = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  azure_serviceprincipal = [{
    application_id       = null
    authentication_token = null
    tenant_id            = null
  }]

  azure_userpass = [{
    password    = null
    tenant_name = null
    username    = null
  }]

  gcp_credentials = [{
    service_account_keyfile_data = null
  }]

  oci_credentials = [{
    fingerprint = null
    key_content = null
    pass_phrase = null
    user        = null
  }]

  tencent_credentials = [{
    secret_id  = null
    secret_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_serviceprincipal" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      application_id       = string
      authentication_token = string
      tenant_id            = string
    }
  ))
  default = []
}

variable "azure_userpass" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      password    = string
      tenant_name = string
      username    = string
    }
  ))
  default = []
}

variable "gcp_credentials" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      service_account_keyfile_data = string
    }
  ))
  default = []
}

variable "oci_credentials" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      fingerprint = string
      key_content = string
      pass_phrase = string
      user        = string
    }
  ))
  default = []
}

variable "tencent_credentials" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      secret_id  = string
      secret_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_cloudconnectoruser" "this" {
  name        = var.name
  password    = var.password
  private_key = var.private_key
  public_key  = var.public_key
  tenant_ref  = var.tenant_ref
  uuid        = var.uuid

  dynamic "azure_serviceprincipal" {
    for_each = var.azure_serviceprincipal
    content {
      application_id       = azure_serviceprincipal.value["application_id"]
      authentication_token = azure_serviceprincipal.value["authentication_token"]
      tenant_id            = azure_serviceprincipal.value["tenant_id"]
    }
  }

  dynamic "azure_userpass" {
    for_each = var.azure_userpass
    content {
      password    = azure_userpass.value["password"]
      tenant_name = azure_userpass.value["tenant_name"]
      username    = azure_userpass.value["username"]
    }
  }

  dynamic "gcp_credentials" {
    for_each = var.gcp_credentials
    content {
      service_account_keyfile_data = gcp_credentials.value["service_account_keyfile_data"]
    }
  }

  dynamic "oci_credentials" {
    for_each = var.oci_credentials
    content {
      fingerprint = oci_credentials.value["fingerprint"]
      key_content = oci_credentials.value["key_content"]
      pass_phrase = oci_credentials.value["pass_phrase"]
      user        = oci_credentials.value["user"]
    }
  }

  dynamic "tencent_credentials" {
    for_each = var.tencent_credentials
    content {
      secret_id  = tencent_credentials.value["secret_id"]
      secret_key = tencent_credentials.value["secret_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_cloudconnectoruser.this.id
}

output "password" {
  description = "returns a string"
  value       = avi_cloudconnectoruser.this.password
}

output "private_key" {
  description = "returns a string"
  value       = avi_cloudconnectoruser.this.private_key
}

output "public_key" {
  description = "returns a string"
  value       = avi_cloudconnectoruser.this.public_key
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_cloudconnectoruser.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_cloudconnectoruser.this.uuid
}

output "this" {
  value = avi_cloudconnectoruser.this
}
```

[top](#index)