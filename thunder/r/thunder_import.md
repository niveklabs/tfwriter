# thunder_import

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_import" {
  source = "./modules/thunder/r/thunder_import"

  # aflex - (optional) is a type of string
  aflex = null
  # auth_jwks - (optional) is a type of string
  auth_jwks = null
  # auth_portal - (optional) is a type of string
  auth_portal = null
  # auth_portal_image - (optional) is a type of string
  auth_portal_image = null
  # bw_list - (optional) is a type of string
  bw_list = null
  # ca_cert - (optional) is a type of string
  ca_cert = null
  # certificate_type - (optional) is a type of string
  certificate_type = null
  # class_list - (optional) is a type of string
  class_list = null
  # class_list_convert - (optional) is a type of string
  class_list_convert = null
  # class_list_type - (optional) is a type of string
  class_list_type = null
  # cloud_config - (optional) is a type of string
  cloud_config = null
  # cloud_creds - (optional) is a type of string
  cloud_creds = null
  # dnssec_dnskey - (optional) is a type of string
  dnssec_dnskey = null
  # dnssec_ds - (optional) is a type of string
  dnssec_ds = null
  # file_inspection_bw_list - (optional) is a type of string
  file_inspection_bw_list = null
  # geo_location - (optional) is a type of string
  geo_location = null
  # glm_cert - (optional) is a type of string
  glm_cert = null
  # glm_license - (optional) is a type of string
  glm_license = null
  # ip_map_list - (optional) is a type of string
  ip_map_list = null
  # local_uri_file - (optional) is a type of string
  local_uri_file = null
  # lw_4o6 - (optional) is a type of string
  lw_4o6 = null
  # overwrite - (optional) is a type of number
  overwrite = null
  # password - (optional) is a type of string
  password = null
  # pfx_password - (optional) is a type of string
  pfx_password = null
  # policy - (optional) is a type of string
  policy = null
  # remote_file - (optional) is a type of string
  remote_file = null
  # secured - (optional) is a type of number
  secured = null
  # ssl_cert - (optional) is a type of string
  ssl_cert = null
  # ssl_cert_key - (optional) is a type of string
  ssl_cert_key = null
  # ssl_crl - (optional) is a type of string
  ssl_crl = null
  # ssl_key - (optional) is a type of string
  ssl_key = null
  # store_name - (optional) is a type of string
  store_name = null
  # terminal - (optional) is a type of number
  terminal = null
  # thales_kmdata - (optional) is a type of string
  thales_kmdata = null
  # thales_secworld - (optional) is a type of string
  thales_secworld = null
  # usb_license - (optional) is a type of string
  usb_license = null
  # use_mgmt_port - (optional) is a type of number
  use_mgmt_port = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # web_category_license - (optional) is a type of string
  web_category_license = null
  # wsdl - (optional) is a type of string
  wsdl = null
  # xml_schema - (optional) is a type of string
  xml_schema = null

  auth_saml_idp = [{
    overwrite            = null
    password             = null
    remote_file          = null
    saml_idp_name        = null
    use_mgmt_port        = null
    verify_xml_signature = null
  }]

  health_external = [{
    description      = null
    externalfilename = null
    overwrite        = null
    password         = null
    remote_file      = null
    use_mgmt_port    = null
  }]

  health_postfile = [{
    overwrite     = null
    password      = null
    postfilename  = null
    remote_file   = null
    use_mgmt_port = null
  }]

  store = [{
    create      = null
    delete      = null
    name        = null
    remote_file = null
  }]

  to_device = [{
    device               = null
    glm_cert             = null
    glm_license          = null
    overwrite            = null
    remote_file          = null
    use_mgmt_port        = null
    web_category_license = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aflex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_jwks" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_portal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_portal_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bw_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "class_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "class_list_convert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "class_list_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_creds" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnssec_dnskey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnssec_ds" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_inspection_bw_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geo_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "glm_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "glm_license" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_map_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_uri_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lw_4o6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "overwrite" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pfx_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secured" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_cert_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_crl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "store_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "terminal" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "thales_kmdata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "thales_secworld" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usb_license" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_mgmt_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_category_license" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wsdl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "xml_schema" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_saml_idp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      overwrite            = number
      password             = string
      remote_file          = string
      saml_idp_name        = string
      use_mgmt_port        = number
      verify_xml_signature = number
    }
  ))
  default = []
}

variable "health_external" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description      = string
      externalfilename = string
      overwrite        = number
      password         = string
      remote_file      = string
      use_mgmt_port    = number
    }
  ))
  default = []
}

variable "health_postfile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      overwrite     = number
      password      = string
      postfilename  = string
      remote_file   = string
      use_mgmt_port = number
    }
  ))
  default = []
}

variable "store" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      create      = number
      delete      = number
      name        = string
      remote_file = string
    }
  ))
  default = []
}

variable "to_device" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      device               = number
      glm_cert             = string
      glm_license          = string
      overwrite            = number
      remote_file          = string
      use_mgmt_port        = number
      web_category_license = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_import" "this" {
  aflex                   = var.aflex
  auth_jwks               = var.auth_jwks
  auth_portal             = var.auth_portal
  auth_portal_image       = var.auth_portal_image
  bw_list                 = var.bw_list
  ca_cert                 = var.ca_cert
  certificate_type        = var.certificate_type
  class_list              = var.class_list
  class_list_convert      = var.class_list_convert
  class_list_type         = var.class_list_type
  cloud_config            = var.cloud_config
  cloud_creds             = var.cloud_creds
  dnssec_dnskey           = var.dnssec_dnskey
  dnssec_ds               = var.dnssec_ds
  file_inspection_bw_list = var.file_inspection_bw_list
  geo_location            = var.geo_location
  glm_cert                = var.glm_cert
  glm_license             = var.glm_license
  ip_map_list             = var.ip_map_list
  local_uri_file          = var.local_uri_file
  lw_4o6                  = var.lw_4o6
  overwrite               = var.overwrite
  password                = var.password
  pfx_password            = var.pfx_password
  policy                  = var.policy
  remote_file             = var.remote_file
  secured                 = var.secured
  ssl_cert                = var.ssl_cert
  ssl_cert_key            = var.ssl_cert_key
  ssl_crl                 = var.ssl_crl
  ssl_key                 = var.ssl_key
  store_name              = var.store_name
  terminal                = var.terminal
  thales_kmdata           = var.thales_kmdata
  thales_secworld         = var.thales_secworld
  usb_license             = var.usb_license
  use_mgmt_port           = var.use_mgmt_port
  user_tag                = var.user_tag
  web_category_license    = var.web_category_license
  wsdl                    = var.wsdl
  xml_schema              = var.xml_schema

  dynamic "auth_saml_idp" {
    for_each = var.auth_saml_idp
    content {
      overwrite            = auth_saml_idp.value["overwrite"]
      password             = auth_saml_idp.value["password"]
      remote_file          = auth_saml_idp.value["remote_file"]
      saml_idp_name        = auth_saml_idp.value["saml_idp_name"]
      use_mgmt_port        = auth_saml_idp.value["use_mgmt_port"]
      verify_xml_signature = auth_saml_idp.value["verify_xml_signature"]
    }
  }

  dynamic "health_external" {
    for_each = var.health_external
    content {
      description      = health_external.value["description"]
      externalfilename = health_external.value["externalfilename"]
      overwrite        = health_external.value["overwrite"]
      password         = health_external.value["password"]
      remote_file      = health_external.value["remote_file"]
      use_mgmt_port    = health_external.value["use_mgmt_port"]
    }
  }

  dynamic "health_postfile" {
    for_each = var.health_postfile
    content {
      overwrite     = health_postfile.value["overwrite"]
      password      = health_postfile.value["password"]
      postfilename  = health_postfile.value["postfilename"]
      remote_file   = health_postfile.value["remote_file"]
      use_mgmt_port = health_postfile.value["use_mgmt_port"]
    }
  }

  dynamic "store" {
    for_each = var.store
    content {
      create      = store.value["create"]
      delete      = store.value["delete"]
      name        = store.value["name"]
      remote_file = store.value["remote_file"]
    }
  }

  dynamic "to_device" {
    for_each = var.to_device
    content {
      device               = to_device.value["device"]
      glm_cert             = to_device.value["glm_cert"]
      glm_license          = to_device.value["glm_license"]
      overwrite            = to_device.value["overwrite"]
      remote_file          = to_device.value["remote_file"]
      use_mgmt_port        = to_device.value["use_mgmt_port"]
      web_category_license = to_device.value["web_category_license"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_config" {
  description = "returns a string"
  value       = thunder_import.this.cloud_config
}

output "cloud_creds" {
  description = "returns a string"
  value       = thunder_import.this.cloud_creds
}

output "id" {
  description = "returns a string"
  value       = thunder_import.this.id
}

output "overwrite" {
  description = "returns a number"
  value       = thunder_import.this.overwrite
}

output "password" {
  description = "returns a string"
  value       = thunder_import.this.password
}

output "remote_file" {
  description = "returns a string"
  value       = thunder_import.this.remote_file
}

output "ssl_key" {
  description = "returns a string"
  value       = thunder_import.this.ssl_key
}

output "use_mgmt_port" {
  description = "returns a number"
  value       = thunder_import.this.use_mgmt_port
}

output "this" {
  value = thunder_import.this
}
```

[top](#index)