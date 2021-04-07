# tencentcloud_cos_bucket_policy

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
module "tencentcloud_cos_bucket_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_cos_bucket_policy"

  # bucket - (required) is a type of string
  bucket = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required) - The name of a bucket to be created. Bucket format should be [custom name]-[appid], for example `mycos-1258798060`."
  type        = string
}

variable "policy" {
  description = "(required) - The text of the policy. For more info please refer to [Tencent official doc](https://intl.cloud.tencent.com/document/product/436/18023)."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cos_bucket_policy" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # policy - (required) is a type of string
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket_policy.this.id
}

output "this" {
  value = tencentcloud_cos_bucket_policy.this
}
```

[top](#index)