# tencentcloud_ssl_pay_certificate

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_ssl_pay_certificate" {
  source = "./modules/tencentcloud/r/tencentcloud_ssl_pay_certificate"

  # alias - (optional) is a type of string
  alias = null
  # domain_num - (required) is a type of number
  domain_num = null
  # product_id - (required) is a type of number
  product_id = null
  # project_id - (optional) is a type of number
  project_id = null
  # time_span - (optional) is a type of number
  time_span = null

  information = [{
    admin_email           = null
    admin_first_name      = null
    admin_last_name       = null
    admin_phone_num       = null
    admin_position        = null
    certificate_domain    = null
    contact_email         = null
    contact_first_name    = null
    contact_last_name     = null
    contact_number        = null
    contact_position      = null
    csr_content           = null
    csr_type              = null
    domain_list           = []
    key_password          = null
    organization_address  = null
    organization_city     = null
    organization_country  = null
    organization_division = null
    organization_name     = null
    organization_region   = null
    phone_area_code       = null
    phone_number          = null
    postal_code           = null
    verify_type           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alias" {
  description = "(optional) - Remark name."
  type        = string
  default     = null
}

variable "domain_num" {
  description = "(required) - Number of domain names included in the certificate."
  type        = number
}

variable "product_id" {
  description = "(required) - Certificate commodity ID. Valid value ranges: (3~42). `3` means SecureSite Enhanced Enterprise Edition (EV Pro), `4` means SecureSite Enhanced (EV), `5` means SecureSite Enterprise Professional Edition (OV Pro), `6` means SecureSite Enterprise (OV), `7` means SecureSite Enterprise Type (OV) wildcard, `8` means Geotrust enhanced (EV), `9` means Geotrust enterprise (OV), `10` means Geotrust enterprise (OV) wildcard, `11` means TrustAsia domain type multi-domain SSL certificate, `12` means TrustAsia domain type ( DV) wildcard, `13` means TrustAsia enterprise wildcard (OV) SSL certificate (D3), `14` means TrustAsia enterprise (OV) SSL certificate (D3), `15` means TrustAsia enterprise multi-domain (OV) SSL certificate (D3), `16` means TrustAsia Enhanced (EV) SSL Certificate (D3), `17` means TrustAsia Enhanced Multiple Domain (EV) SSL Certificate (D3), `18` means GlobalSign Enterprise (OV) SSL Certificate, `19` means GlobalSign Enterprise Wildcard (OV) SSL Certificate, `20` means GlobalSign Enhanced (EV) SSL Certificate, `21` means TrustAsia Enterprise Wildcard Multiple Domain (OV) SSL Certificate (D3), `22` means GlobalSign Enterprise Multiple Domain (OV) SSL Certificate, `23` means GlobalSign Enterprise Multiple Wildcard Domain name (OV) SSL certificate, `24` means GlobalSign enhanced multi-domain (EV) SSL certificate, `25` means Wotrus domain type certificate, `26` means Wotrus domain type multi-domain certificate, `27` means Wotrus domain type wildcard certificate, `28` means Wotrus enterprise type certificate, `29` means Wotrus enterprise multi-domain certificate, `30` means Wotrus enterprise wildcard certificate, `31` means Wotrus enhanced certificate, `32` means Wotrus enhanced multi-domain certificate, `33` means DNSPod national secret domain name certificate, `34` means DNSPod national secret domain name certificate Multi-domain certificate, `35` means DNSPod national secret domain name wildcard certificate, `37` means DNSPod national secret enterprise certificate, `38` means DNSPod national secret enterprise multi-domain certificate, `39` means DNSPod national secret enterprise wildcard certificate, `40` means DNSPod national secret increase Strong certificate, `41` means DNSPod national secret enhanced multi-domain certificate, `42` means TrustAsia domain-type wildcard multi-domain certificate."
  type        = number
}

variable "project_id" {
  description = "(optional) - The ID of project."
  type        = number
  default     = null
}

variable "time_span" {
  description = "(optional) - Certificate period, currently only supports 1 year certificate purchase."
  type        = number
  default     = null
}

variable "information" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin_email           = string
      admin_first_name      = string
      admin_last_name       = string
      admin_phone_num       = string
      admin_position        = string
      certificate_domain    = string
      contact_email         = string
      contact_first_name    = string
      contact_last_name     = string
      contact_number        = string
      contact_position      = string
      csr_content           = string
      csr_type              = string
      domain_list           = set(string)
      key_password          = string
      organization_address  = string
      organization_city     = string
      organization_country  = string
      organization_division = string
      organization_name     = string
      organization_region   = string
      phone_area_code       = string
      phone_number          = string
      postal_code           = string
      verify_type           = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ssl_pay_certificate" "this" {
  alias      = var.alias
  domain_num = var.domain_num
  product_id = var.product_id
  project_id = var.project_id
  time_span  = var.time_span

  dynamic "information" {
    for_each = var.information
    content {
      admin_email           = information.value["admin_email"]
      admin_first_name      = information.value["admin_first_name"]
      admin_last_name       = information.value["admin_last_name"]
      admin_phone_num       = information.value["admin_phone_num"]
      admin_position        = information.value["admin_position"]
      certificate_domain    = information.value["certificate_domain"]
      contact_email         = information.value["contact_email"]
      contact_first_name    = information.value["contact_first_name"]
      contact_last_name     = information.value["contact_last_name"]
      contact_number        = information.value["contact_number"]
      contact_position      = information.value["contact_position"]
      csr_content           = information.value["csr_content"]
      csr_type              = information.value["csr_type"]
      domain_list           = information.value["domain_list"]
      key_password          = information.value["key_password"]
      organization_address  = information.value["organization_address"]
      organization_city     = information.value["organization_city"]
      organization_country  = information.value["organization_country"]
      organization_division = information.value["organization_division"]
      organization_name     = information.value["organization_name"]
      organization_region   = information.value["organization_region"]
      phone_area_code       = information.value["phone_area_code"]
      phone_number          = information.value["phone_number"]
      postal_code           = information.value["postal_code"]
      verify_type           = information.value["verify_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alias" {
  description = "returns a string"
  value       = tencentcloud_ssl_pay_certificate.this.alias
}

output "certificate_id" {
  description = "returns a string"
  value       = tencentcloud_ssl_pay_certificate.this.certificate_id
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ssl_pay_certificate.this.id
}

output "order_id" {
  description = "returns a string"
  value       = tencentcloud_ssl_pay_certificate.this.order_id
}

output "project_id" {
  description = "returns a number"
  value       = tencentcloud_ssl_pay_certificate.this.project_id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_ssl_pay_certificate.this.status
}

output "this" {
  value = tencentcloud_ssl_pay_certificate.this
}
```

[top](#index)