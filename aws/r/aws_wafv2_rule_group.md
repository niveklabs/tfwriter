# aws_wafv2_rule_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_wafv2_rule_group" {
  source = "./modules/aws/r/aws_wafv2_rule_group"

  # capacity - (required) is a type of number
  capacity = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
  # tags - (optional) is a type of map of string
  tags = {}

  rule = [{
    action = [{
      allow = [{

      }]
      block = [{

      }]
      count = [{

      }]
    }]
    name     = null
    priority = null
    statement = [{
      and_statement = [{
        statement = [{
          and_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          byte_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            positional_constraint = null
            search_string         = null
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          geo_match_statement = [{
            country_codes = []
            forwarded_ip_config = [{
              fallback_behavior = null
              header_name       = null
            }]
          }]
          ip_set_reference_statement = [{
            arn = null
            ip_set_forwarded_ip_config = [{
              fallback_behavior = null
              header_name       = null
              position          = null
            }]
          }]
          not_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          or_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          regex_pattern_set_reference_statement = [{
            arn = null
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          size_constraint_statement = [{
            comparison_operator = null
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            size = null
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          sqli_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          xss_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
        }]
      }]
      byte_match_statement = [{
        field_to_match = [{
          all_query_arguments = [{

          }]
          body = [{

          }]
          method = [{

          }]
          query_string = [{

          }]
          single_header = [{
            name = null
          }]
          single_query_argument = [{
            name = null
          }]
          uri_path = [{

          }]
        }]
        positional_constraint = null
        search_string         = null
        text_transformation = [{
          priority = null
          type     = null
        }]
      }]
      geo_match_statement = [{
        country_codes = []
        forwarded_ip_config = [{
          fallback_behavior = null
          header_name       = null
        }]
      }]
      ip_set_reference_statement = [{
        arn = null
        ip_set_forwarded_ip_config = [{
          fallback_behavior = null
          header_name       = null
          position          = null
        }]
      }]
      not_statement = [{
        statement = [{
          and_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          byte_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            positional_constraint = null
            search_string         = null
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          geo_match_statement = [{
            country_codes = []
            forwarded_ip_config = [{
              fallback_behavior = null
              header_name       = null
            }]
          }]
          ip_set_reference_statement = [{
            arn = null
            ip_set_forwarded_ip_config = [{
              fallback_behavior = null
              header_name       = null
              position          = null
            }]
          }]
          not_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          or_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          regex_pattern_set_reference_statement = [{
            arn = null
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          size_constraint_statement = [{
            comparison_operator = null
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            size = null
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          sqli_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          xss_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
        }]
      }]
      or_statement = [{
        statement = [{
          and_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          byte_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            positional_constraint = null
            search_string         = null
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          geo_match_statement = [{
            country_codes = []
            forwarded_ip_config = [{
              fallback_behavior = null
              header_name       = null
            }]
          }]
          ip_set_reference_statement = [{
            arn = null
            ip_set_forwarded_ip_config = [{
              fallback_behavior = null
              header_name       = null
              position          = null
            }]
          }]
          not_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          or_statement = [{
            statement = [{
              byte_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                positional_constraint = null
                search_string         = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              geo_match_statement = [{
                country_codes = []
                forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                }]
              }]
              ip_set_reference_statement = [{
                arn = null
                ip_set_forwarded_ip_config = [{
                  fallback_behavior = null
                  header_name       = null
                  position          = null
                }]
              }]
              regex_pattern_set_reference_statement = [{
                arn = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              size_constraint_statement = [{
                comparison_operator = null
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                size = null
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              sqli_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
              xss_match_statement = [{
                field_to_match = [{
                  all_query_arguments = [{

                  }]
                  body = [{

                  }]
                  method = [{

                  }]
                  query_string = [{

                  }]
                  single_header = [{
                    name = null
                  }]
                  single_query_argument = [{
                    name = null
                  }]
                  uri_path = [{

                  }]
                }]
                text_transformation = [{
                  priority = null
                  type     = null
                }]
              }]
            }]
          }]
          regex_pattern_set_reference_statement = [{
            arn = null
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          size_constraint_statement = [{
            comparison_operator = null
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            size = null
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          sqli_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
          xss_match_statement = [{
            field_to_match = [{
              all_query_arguments = [{

              }]
              body = [{

              }]
              method = [{

              }]
              query_string = [{

              }]
              single_header = [{
                name = null
              }]
              single_query_argument = [{
                name = null
              }]
              uri_path = [{

              }]
            }]
            text_transformation = [{
              priority = null
              type     = null
            }]
          }]
        }]
      }]
      regex_pattern_set_reference_statement = [{
        arn = null
        field_to_match = [{
          all_query_arguments = [{

          }]
          body = [{

          }]
          method = [{

          }]
          query_string = [{

          }]
          single_header = [{
            name = null
          }]
          single_query_argument = [{
            name = null
          }]
          uri_path = [{

          }]
        }]
        text_transformation = [{
          priority = null
          type     = null
        }]
      }]
      size_constraint_statement = [{
        comparison_operator = null
        field_to_match = [{
          all_query_arguments = [{

          }]
          body = [{

          }]
          method = [{

          }]
          query_string = [{

          }]
          single_header = [{
            name = null
          }]
          single_query_argument = [{
            name = null
          }]
          uri_path = [{

          }]
        }]
        size = null
        text_transformation = [{
          priority = null
          type     = null
        }]
      }]
      sqli_match_statement = [{
        field_to_match = [{
          all_query_arguments = [{

          }]
          body = [{

          }]
          method = [{

          }]
          query_string = [{

          }]
          single_header = [{
            name = null
          }]
          single_query_argument = [{
            name = null
          }]
          uri_path = [{

          }]
        }]
        text_transformation = [{
          priority = null
          type     = null
        }]
      }]
      xss_match_statement = [{
        field_to_match = [{
          all_query_arguments = [{

          }]
          body = [{

          }]
          method = [{

          }]
          query_string = [{

          }]
          single_header = [{
            name = null
          }]
          single_query_argument = [{
            name = null
          }]
          uri_path = [{

          }]
        }]
        text_transformation = [{
          priority = null
          type     = null
        }]
      }]
    }]
    visibility_config = [{
      cloudwatch_metrics_enabled = null
      metric_name                = null
      sampled_requests_enabled   = null
    }]
  }]

  visibility_config = [{
    cloudwatch_metrics_enabled = null
    metric_name                = null
    sampled_requests_enabled   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "capacity" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          allow = list(object(
            {

            }
          ))
          block = list(object(
            {

            }
          ))
          count = list(object(
            {

            }
          ))
        }
      ))
      name     = string
      priority = number
      statement = list(object(
        {
          and_statement = list(object(
            {
              statement = list(object(
                {
                  and_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  byte_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      positional_constraint = string
                      search_string         = string
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  geo_match_statement = list(object(
                    {
                      country_codes = list(string)
                      forwarded_ip_config = list(object(
                        {
                          fallback_behavior = string
                          header_name       = string
                        }
                      ))
                    }
                  ))
                  ip_set_reference_statement = list(object(
                    {
                      arn = string
                      ip_set_forwarded_ip_config = list(object(
                        {
                          fallback_behavior = string
                          header_name       = string
                          position          = string
                        }
                      ))
                    }
                  ))
                  not_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  or_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  regex_pattern_set_reference_statement = list(object(
                    {
                      arn = string
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  size_constraint_statement = list(object(
                    {
                      comparison_operator = string
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      size = number
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  sqli_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  xss_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                }
              ))
            }
          ))
          byte_match_statement = list(object(
            {
              field_to_match = list(object(
                {
                  all_query_arguments = list(object(
                    {

                    }
                  ))
                  body = list(object(
                    {

                    }
                  ))
                  method = list(object(
                    {

                    }
                  ))
                  query_string = list(object(
                    {

                    }
                  ))
                  single_header = list(object(
                    {
                      name = string
                    }
                  ))
                  single_query_argument = list(object(
                    {
                      name = string
                    }
                  ))
                  uri_path = list(object(
                    {

                    }
                  ))
                }
              ))
              positional_constraint = string
              search_string         = string
              text_transformation = set(object(
                {
                  priority = number
                  type     = string
                }
              ))
            }
          ))
          geo_match_statement = list(object(
            {
              country_codes = list(string)
              forwarded_ip_config = list(object(
                {
                  fallback_behavior = string
                  header_name       = string
                }
              ))
            }
          ))
          ip_set_reference_statement = list(object(
            {
              arn = string
              ip_set_forwarded_ip_config = list(object(
                {
                  fallback_behavior = string
                  header_name       = string
                  position          = string
                }
              ))
            }
          ))
          not_statement = list(object(
            {
              statement = list(object(
                {
                  and_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  byte_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      positional_constraint = string
                      search_string         = string
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  geo_match_statement = list(object(
                    {
                      country_codes = list(string)
                      forwarded_ip_config = list(object(
                        {
                          fallback_behavior = string
                          header_name       = string
                        }
                      ))
                    }
                  ))
                  ip_set_reference_statement = list(object(
                    {
                      arn = string
                      ip_set_forwarded_ip_config = list(object(
                        {
                          fallback_behavior = string
                          header_name       = string
                          position          = string
                        }
                      ))
                    }
                  ))
                  not_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  or_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  regex_pattern_set_reference_statement = list(object(
                    {
                      arn = string
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  size_constraint_statement = list(object(
                    {
                      comparison_operator = string
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      size = number
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  sqli_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  xss_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                }
              ))
            }
          ))
          or_statement = list(object(
            {
              statement = list(object(
                {
                  and_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  byte_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      positional_constraint = string
                      search_string         = string
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  geo_match_statement = list(object(
                    {
                      country_codes = list(string)
                      forwarded_ip_config = list(object(
                        {
                          fallback_behavior = string
                          header_name       = string
                        }
                      ))
                    }
                  ))
                  ip_set_reference_statement = list(object(
                    {
                      arn = string
                      ip_set_forwarded_ip_config = list(object(
                        {
                          fallback_behavior = string
                          header_name       = string
                          position          = string
                        }
                      ))
                    }
                  ))
                  not_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  or_statement = list(object(
                    {
                      statement = list(object(
                        {
                          byte_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              positional_constraint = string
                              search_string         = string
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          geo_match_statement = list(object(
                            {
                              country_codes = list(string)
                              forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                }
                              ))
                            }
                          ))
                          ip_set_reference_statement = list(object(
                            {
                              arn = string
                              ip_set_forwarded_ip_config = list(object(
                                {
                                  fallback_behavior = string
                                  header_name       = string
                                  position          = string
                                }
                              ))
                            }
                          ))
                          regex_pattern_set_reference_statement = list(object(
                            {
                              arn = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          size_constraint_statement = list(object(
                            {
                              comparison_operator = string
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              size = number
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          sqli_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                          xss_match_statement = list(object(
                            {
                              field_to_match = list(object(
                                {
                                  all_query_arguments = list(object(
                                    {

                                    }
                                  ))
                                  body = list(object(
                                    {

                                    }
                                  ))
                                  method = list(object(
                                    {

                                    }
                                  ))
                                  query_string = list(object(
                                    {

                                    }
                                  ))
                                  single_header = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  single_query_argument = list(object(
                                    {
                                      name = string
                                    }
                                  ))
                                  uri_path = list(object(
                                    {

                                    }
                                  ))
                                }
                              ))
                              text_transformation = set(object(
                                {
                                  priority = number
                                  type     = string
                                }
                              ))
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  regex_pattern_set_reference_statement = list(object(
                    {
                      arn = string
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  size_constraint_statement = list(object(
                    {
                      comparison_operator = string
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      size = number
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  sqli_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                  xss_match_statement = list(object(
                    {
                      field_to_match = list(object(
                        {
                          all_query_arguments = list(object(
                            {

                            }
                          ))
                          body = list(object(
                            {

                            }
                          ))
                          method = list(object(
                            {

                            }
                          ))
                          query_string = list(object(
                            {

                            }
                          ))
                          single_header = list(object(
                            {
                              name = string
                            }
                          ))
                          single_query_argument = list(object(
                            {
                              name = string
                            }
                          ))
                          uri_path = list(object(
                            {

                            }
                          ))
                        }
                      ))
                      text_transformation = set(object(
                        {
                          priority = number
                          type     = string
                        }
                      ))
                    }
                  ))
                }
              ))
            }
          ))
          regex_pattern_set_reference_statement = list(object(
            {
              arn = string
              field_to_match = list(object(
                {
                  all_query_arguments = list(object(
                    {

                    }
                  ))
                  body = list(object(
                    {

                    }
                  ))
                  method = list(object(
                    {

                    }
                  ))
                  query_string = list(object(
                    {

                    }
                  ))
                  single_header = list(object(
                    {
                      name = string
                    }
                  ))
                  single_query_argument = list(object(
                    {
                      name = string
                    }
                  ))
                  uri_path = list(object(
                    {

                    }
                  ))
                }
              ))
              text_transformation = set(object(
                {
                  priority = number
                  type     = string
                }
              ))
            }
          ))
          size_constraint_statement = list(object(
            {
              comparison_operator = string
              field_to_match = list(object(
                {
                  all_query_arguments = list(object(
                    {

                    }
                  ))
                  body = list(object(
                    {

                    }
                  ))
                  method = list(object(
                    {

                    }
                  ))
                  query_string = list(object(
                    {

                    }
                  ))
                  single_header = list(object(
                    {
                      name = string
                    }
                  ))
                  single_query_argument = list(object(
                    {
                      name = string
                    }
                  ))
                  uri_path = list(object(
                    {

                    }
                  ))
                }
              ))
              size = number
              text_transformation = set(object(
                {
                  priority = number
                  type     = string
                }
              ))
            }
          ))
          sqli_match_statement = list(object(
            {
              field_to_match = list(object(
                {
                  all_query_arguments = list(object(
                    {

                    }
                  ))
                  body = list(object(
                    {

                    }
                  ))
                  method = list(object(
                    {

                    }
                  ))
                  query_string = list(object(
                    {

                    }
                  ))
                  single_header = list(object(
                    {
                      name = string
                    }
                  ))
                  single_query_argument = list(object(
                    {
                      name = string
                    }
                  ))
                  uri_path = list(object(
                    {

                    }
                  ))
                }
              ))
              text_transformation = set(object(
                {
                  priority = number
                  type     = string
                }
              ))
            }
          ))
          xss_match_statement = list(object(
            {
              field_to_match = list(object(
                {
                  all_query_arguments = list(object(
                    {

                    }
                  ))
                  body = list(object(
                    {

                    }
                  ))
                  method = list(object(
                    {

                    }
                  ))
                  query_string = list(object(
                    {

                    }
                  ))
                  single_header = list(object(
                    {
                      name = string
                    }
                  ))
                  single_query_argument = list(object(
                    {
                      name = string
                    }
                  ))
                  uri_path = list(object(
                    {

                    }
                  ))
                }
              ))
              text_transformation = set(object(
                {
                  priority = number
                  type     = string
                }
              ))
            }
          ))
        }
      ))
      visibility_config = list(object(
        {
          cloudwatch_metrics_enabled = bool
          metric_name                = string
          sampled_requests_enabled   = bool
        }
      ))
    }
  ))
  default = []
}

variable "visibility_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cloudwatch_metrics_enabled = bool
      metric_name                = string
      sampled_requests_enabled   = bool
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafv2_rule_group" "this" {
  capacity    = var.capacity
  description = var.description
  name        = var.name
  scope       = var.scope
  tags        = var.tags

  dynamic "rule" {
    for_each = var.rule
    content {
      name     = rule.value["name"]
      priority = rule.value["priority"]

      dynamic "action" {
        for_each = rule.value.action
        content {

          dynamic "allow" {
            for_each = action.value.allow
            content {
            }
          }

          dynamic "block" {
            for_each = action.value.block
            content {
            }
          }

          dynamic "count" {
            for_each = action.value.count
            content {
            }
          }

        }
      }

      dynamic "statement" {
        for_each = rule.value.statement
        content {

          dynamic "and_statement" {
            for_each = statement.value.and_statement
            content {

              dynamic "statement" {
                for_each = and_statement.value.statement
                content {

                  dynamic "and_statement" {
                    for_each = statement.value.and_statement
                    content {

                      dynamic "statement" {
                        for_each = and_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "byte_match_statement" {
                    for_each = statement.value.byte_match_statement
                    content {
                      positional_constraint = byte_match_statement.value["positional_constraint"]
                      search_string         = byte_match_statement.value["search_string"]

                      dynamic "field_to_match" {
                        for_each = byte_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = byte_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "geo_match_statement" {
                    for_each = statement.value.geo_match_statement
                    content {
                      country_codes = geo_match_statement.value["country_codes"]

                      dynamic "forwarded_ip_config" {
                        for_each = geo_match_statement.value.forwarded_ip_config
                        content {
                          fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                          header_name       = forwarded_ip_config.value["header_name"]
                        }
                      }

                    }
                  }

                  dynamic "ip_set_reference_statement" {
                    for_each = statement.value.ip_set_reference_statement
                    content {
                      arn = ip_set_reference_statement.value["arn"]

                      dynamic "ip_set_forwarded_ip_config" {
                        for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                        content {
                          fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                          header_name       = ip_set_forwarded_ip_config.value["header_name"]
                          position          = ip_set_forwarded_ip_config.value["position"]
                        }
                      }

                    }
                  }

                  dynamic "not_statement" {
                    for_each = statement.value.not_statement
                    content {

                      dynamic "statement" {
                        for_each = not_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "or_statement" {
                    for_each = statement.value.or_statement
                    content {

                      dynamic "statement" {
                        for_each = or_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "regex_pattern_set_reference_statement" {
                    for_each = statement.value.regex_pattern_set_reference_statement
                    content {
                      arn = regex_pattern_set_reference_statement.value["arn"]

                      dynamic "field_to_match" {
                        for_each = regex_pattern_set_reference_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = regex_pattern_set_reference_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "size_constraint_statement" {
                    for_each = statement.value.size_constraint_statement
                    content {
                      comparison_operator = size_constraint_statement.value["comparison_operator"]
                      size                = size_constraint_statement.value["size"]

                      dynamic "field_to_match" {
                        for_each = size_constraint_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = size_constraint_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "sqli_match_statement" {
                    for_each = statement.value.sqli_match_statement
                    content {

                      dynamic "field_to_match" {
                        for_each = sqli_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = sqli_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "xss_match_statement" {
                    for_each = statement.value.xss_match_statement
                    content {

                      dynamic "field_to_match" {
                        for_each = xss_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = xss_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "byte_match_statement" {
            for_each = statement.value.byte_match_statement
            content {
              positional_constraint = byte_match_statement.value["positional_constraint"]
              search_string         = byte_match_statement.value["search_string"]

              dynamic "field_to_match" {
                for_each = byte_match_statement.value.field_to_match
                content {

                  dynamic "all_query_arguments" {
                    for_each = field_to_match.value.all_query_arguments
                    content {
                    }
                  }

                  dynamic "body" {
                    for_each = field_to_match.value.body
                    content {
                    }
                  }

                  dynamic "method" {
                    for_each = field_to_match.value.method
                    content {
                    }
                  }

                  dynamic "query_string" {
                    for_each = field_to_match.value.query_string
                    content {
                    }
                  }

                  dynamic "single_header" {
                    for_each = field_to_match.value.single_header
                    content {
                      name = single_header.value["name"]
                    }
                  }

                  dynamic "single_query_argument" {
                    for_each = field_to_match.value.single_query_argument
                    content {
                      name = single_query_argument.value["name"]
                    }
                  }

                  dynamic "uri_path" {
                    for_each = field_to_match.value.uri_path
                    content {
                    }
                  }

                }
              }

              dynamic "text_transformation" {
                for_each = byte_match_statement.value.text_transformation
                content {
                  priority = text_transformation.value["priority"]
                  type     = text_transformation.value["type"]
                }
              }

            }
          }

          dynamic "geo_match_statement" {
            for_each = statement.value.geo_match_statement
            content {
              country_codes = geo_match_statement.value["country_codes"]

              dynamic "forwarded_ip_config" {
                for_each = geo_match_statement.value.forwarded_ip_config
                content {
                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                  header_name       = forwarded_ip_config.value["header_name"]
                }
              }

            }
          }

          dynamic "ip_set_reference_statement" {
            for_each = statement.value.ip_set_reference_statement
            content {
              arn = ip_set_reference_statement.value["arn"]

              dynamic "ip_set_forwarded_ip_config" {
                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                content {
                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                  position          = ip_set_forwarded_ip_config.value["position"]
                }
              }

            }
          }

          dynamic "not_statement" {
            for_each = statement.value.not_statement
            content {

              dynamic "statement" {
                for_each = not_statement.value.statement
                content {

                  dynamic "and_statement" {
                    for_each = statement.value.and_statement
                    content {

                      dynamic "statement" {
                        for_each = and_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "byte_match_statement" {
                    for_each = statement.value.byte_match_statement
                    content {
                      positional_constraint = byte_match_statement.value["positional_constraint"]
                      search_string         = byte_match_statement.value["search_string"]

                      dynamic "field_to_match" {
                        for_each = byte_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = byte_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "geo_match_statement" {
                    for_each = statement.value.geo_match_statement
                    content {
                      country_codes = geo_match_statement.value["country_codes"]

                      dynamic "forwarded_ip_config" {
                        for_each = geo_match_statement.value.forwarded_ip_config
                        content {
                          fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                          header_name       = forwarded_ip_config.value["header_name"]
                        }
                      }

                    }
                  }

                  dynamic "ip_set_reference_statement" {
                    for_each = statement.value.ip_set_reference_statement
                    content {
                      arn = ip_set_reference_statement.value["arn"]

                      dynamic "ip_set_forwarded_ip_config" {
                        for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                        content {
                          fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                          header_name       = ip_set_forwarded_ip_config.value["header_name"]
                          position          = ip_set_forwarded_ip_config.value["position"]
                        }
                      }

                    }
                  }

                  dynamic "not_statement" {
                    for_each = statement.value.not_statement
                    content {

                      dynamic "statement" {
                        for_each = not_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "or_statement" {
                    for_each = statement.value.or_statement
                    content {

                      dynamic "statement" {
                        for_each = or_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "regex_pattern_set_reference_statement" {
                    for_each = statement.value.regex_pattern_set_reference_statement
                    content {
                      arn = regex_pattern_set_reference_statement.value["arn"]

                      dynamic "field_to_match" {
                        for_each = regex_pattern_set_reference_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = regex_pattern_set_reference_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "size_constraint_statement" {
                    for_each = statement.value.size_constraint_statement
                    content {
                      comparison_operator = size_constraint_statement.value["comparison_operator"]
                      size                = size_constraint_statement.value["size"]

                      dynamic "field_to_match" {
                        for_each = size_constraint_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = size_constraint_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "sqli_match_statement" {
                    for_each = statement.value.sqli_match_statement
                    content {

                      dynamic "field_to_match" {
                        for_each = sqli_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = sqli_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "xss_match_statement" {
                    for_each = statement.value.xss_match_statement
                    content {

                      dynamic "field_to_match" {
                        for_each = xss_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = xss_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "or_statement" {
            for_each = statement.value.or_statement
            content {

              dynamic "statement" {
                for_each = or_statement.value.statement
                content {

                  dynamic "and_statement" {
                    for_each = statement.value.and_statement
                    content {

                      dynamic "statement" {
                        for_each = and_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "byte_match_statement" {
                    for_each = statement.value.byte_match_statement
                    content {
                      positional_constraint = byte_match_statement.value["positional_constraint"]
                      search_string         = byte_match_statement.value["search_string"]

                      dynamic "field_to_match" {
                        for_each = byte_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = byte_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "geo_match_statement" {
                    for_each = statement.value.geo_match_statement
                    content {
                      country_codes = geo_match_statement.value["country_codes"]

                      dynamic "forwarded_ip_config" {
                        for_each = geo_match_statement.value.forwarded_ip_config
                        content {
                          fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                          header_name       = forwarded_ip_config.value["header_name"]
                        }
                      }

                    }
                  }

                  dynamic "ip_set_reference_statement" {
                    for_each = statement.value.ip_set_reference_statement
                    content {
                      arn = ip_set_reference_statement.value["arn"]

                      dynamic "ip_set_forwarded_ip_config" {
                        for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                        content {
                          fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                          header_name       = ip_set_forwarded_ip_config.value["header_name"]
                          position          = ip_set_forwarded_ip_config.value["position"]
                        }
                      }

                    }
                  }

                  dynamic "not_statement" {
                    for_each = statement.value.not_statement
                    content {

                      dynamic "statement" {
                        for_each = not_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "or_statement" {
                    for_each = statement.value.or_statement
                    content {

                      dynamic "statement" {
                        for_each = or_statement.value.statement
                        content {

                          dynamic "byte_match_statement" {
                            for_each = statement.value.byte_match_statement
                            content {
                              positional_constraint = byte_match_statement.value["positional_constraint"]
                              search_string         = byte_match_statement.value["search_string"]

                              dynamic "field_to_match" {
                                for_each = byte_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = byte_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "geo_match_statement" {
                            for_each = statement.value.geo_match_statement
                            content {
                              country_codes = geo_match_statement.value["country_codes"]

                              dynamic "forwarded_ip_config" {
                                for_each = geo_match_statement.value.forwarded_ip_config
                                content {
                                  fallback_behavior = forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = forwarded_ip_config.value["header_name"]
                                }
                              }

                            }
                          }

                          dynamic "ip_set_reference_statement" {
                            for_each = statement.value.ip_set_reference_statement
                            content {
                              arn = ip_set_reference_statement.value["arn"]

                              dynamic "ip_set_forwarded_ip_config" {
                                for_each = ip_set_reference_statement.value.ip_set_forwarded_ip_config
                                content {
                                  fallback_behavior = ip_set_forwarded_ip_config.value["fallback_behavior"]
                                  header_name       = ip_set_forwarded_ip_config.value["header_name"]
                                  position          = ip_set_forwarded_ip_config.value["position"]
                                }
                              }

                            }
                          }

                          dynamic "regex_pattern_set_reference_statement" {
                            for_each = statement.value.regex_pattern_set_reference_statement
                            content {
                              arn = regex_pattern_set_reference_statement.value["arn"]

                              dynamic "field_to_match" {
                                for_each = regex_pattern_set_reference_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = regex_pattern_set_reference_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "size_constraint_statement" {
                            for_each = statement.value.size_constraint_statement
                            content {
                              comparison_operator = size_constraint_statement.value["comparison_operator"]
                              size                = size_constraint_statement.value["size"]

                              dynamic "field_to_match" {
                                for_each = size_constraint_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = size_constraint_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "sqli_match_statement" {
                            for_each = statement.value.sqli_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = sqli_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = sqli_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "xss_match_statement" {
                            for_each = statement.value.xss_match_statement
                            content {

                              dynamic "field_to_match" {
                                for_each = xss_match_statement.value.field_to_match
                                content {

                                  dynamic "all_query_arguments" {
                                    for_each = field_to_match.value.all_query_arguments
                                    content {
                                    }
                                  }

                                  dynamic "body" {
                                    for_each = field_to_match.value.body
                                    content {
                                    }
                                  }

                                  dynamic "method" {
                                    for_each = field_to_match.value.method
                                    content {
                                    }
                                  }

                                  dynamic "query_string" {
                                    for_each = field_to_match.value.query_string
                                    content {
                                    }
                                  }

                                  dynamic "single_header" {
                                    for_each = field_to_match.value.single_header
                                    content {
                                      name = single_header.value["name"]
                                    }
                                  }

                                  dynamic "single_query_argument" {
                                    for_each = field_to_match.value.single_query_argument
                                    content {
                                      name = single_query_argument.value["name"]
                                    }
                                  }

                                  dynamic "uri_path" {
                                    for_each = field_to_match.value.uri_path
                                    content {
                                    }
                                  }

                                }
                              }

                              dynamic "text_transformation" {
                                for_each = xss_match_statement.value.text_transformation
                                content {
                                  priority = text_transformation.value["priority"]
                                  type     = text_transformation.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "regex_pattern_set_reference_statement" {
                    for_each = statement.value.regex_pattern_set_reference_statement
                    content {
                      arn = regex_pattern_set_reference_statement.value["arn"]

                      dynamic "field_to_match" {
                        for_each = regex_pattern_set_reference_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = regex_pattern_set_reference_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "size_constraint_statement" {
                    for_each = statement.value.size_constraint_statement
                    content {
                      comparison_operator = size_constraint_statement.value["comparison_operator"]
                      size                = size_constraint_statement.value["size"]

                      dynamic "field_to_match" {
                        for_each = size_constraint_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = size_constraint_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "sqli_match_statement" {
                    for_each = statement.value.sqli_match_statement
                    content {

                      dynamic "field_to_match" {
                        for_each = sqli_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = sqli_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "xss_match_statement" {
                    for_each = statement.value.xss_match_statement
                    content {

                      dynamic "field_to_match" {
                        for_each = xss_match_statement.value.field_to_match
                        content {

                          dynamic "all_query_arguments" {
                            for_each = field_to_match.value.all_query_arguments
                            content {
                            }
                          }

                          dynamic "body" {
                            for_each = field_to_match.value.body
                            content {
                            }
                          }

                          dynamic "method" {
                            for_each = field_to_match.value.method
                            content {
                            }
                          }

                          dynamic "query_string" {
                            for_each = field_to_match.value.query_string
                            content {
                            }
                          }

                          dynamic "single_header" {
                            for_each = field_to_match.value.single_header
                            content {
                              name = single_header.value["name"]
                            }
                          }

                          dynamic "single_query_argument" {
                            for_each = field_to_match.value.single_query_argument
                            content {
                              name = single_query_argument.value["name"]
                            }
                          }

                          dynamic "uri_path" {
                            for_each = field_to_match.value.uri_path
                            content {
                            }
                          }

                        }
                      }

                      dynamic "text_transformation" {
                        for_each = xss_match_statement.value.text_transformation
                        content {
                          priority = text_transformation.value["priority"]
                          type     = text_transformation.value["type"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "regex_pattern_set_reference_statement" {
            for_each = statement.value.regex_pattern_set_reference_statement
            content {
              arn = regex_pattern_set_reference_statement.value["arn"]

              dynamic "field_to_match" {
                for_each = regex_pattern_set_reference_statement.value.field_to_match
                content {

                  dynamic "all_query_arguments" {
                    for_each = field_to_match.value.all_query_arguments
                    content {
                    }
                  }

                  dynamic "body" {
                    for_each = field_to_match.value.body
                    content {
                    }
                  }

                  dynamic "method" {
                    for_each = field_to_match.value.method
                    content {
                    }
                  }

                  dynamic "query_string" {
                    for_each = field_to_match.value.query_string
                    content {
                    }
                  }

                  dynamic "single_header" {
                    for_each = field_to_match.value.single_header
                    content {
                      name = single_header.value["name"]
                    }
                  }

                  dynamic "single_query_argument" {
                    for_each = field_to_match.value.single_query_argument
                    content {
                      name = single_query_argument.value["name"]
                    }
                  }

                  dynamic "uri_path" {
                    for_each = field_to_match.value.uri_path
                    content {
                    }
                  }

                }
              }

              dynamic "text_transformation" {
                for_each = regex_pattern_set_reference_statement.value.text_transformation
                content {
                  priority = text_transformation.value["priority"]
                  type     = text_transformation.value["type"]
                }
              }

            }
          }

          dynamic "size_constraint_statement" {
            for_each = statement.value.size_constraint_statement
            content {
              comparison_operator = size_constraint_statement.value["comparison_operator"]
              size                = size_constraint_statement.value["size"]

              dynamic "field_to_match" {
                for_each = size_constraint_statement.value.field_to_match
                content {

                  dynamic "all_query_arguments" {
                    for_each = field_to_match.value.all_query_arguments
                    content {
                    }
                  }

                  dynamic "body" {
                    for_each = field_to_match.value.body
                    content {
                    }
                  }

                  dynamic "method" {
                    for_each = field_to_match.value.method
                    content {
                    }
                  }

                  dynamic "query_string" {
                    for_each = field_to_match.value.query_string
                    content {
                    }
                  }

                  dynamic "single_header" {
                    for_each = field_to_match.value.single_header
                    content {
                      name = single_header.value["name"]
                    }
                  }

                  dynamic "single_query_argument" {
                    for_each = field_to_match.value.single_query_argument
                    content {
                      name = single_query_argument.value["name"]
                    }
                  }

                  dynamic "uri_path" {
                    for_each = field_to_match.value.uri_path
                    content {
                    }
                  }

                }
              }

              dynamic "text_transformation" {
                for_each = size_constraint_statement.value.text_transformation
                content {
                  priority = text_transformation.value["priority"]
                  type     = text_transformation.value["type"]
                }
              }

            }
          }

          dynamic "sqli_match_statement" {
            for_each = statement.value.sqli_match_statement
            content {

              dynamic "field_to_match" {
                for_each = sqli_match_statement.value.field_to_match
                content {

                  dynamic "all_query_arguments" {
                    for_each = field_to_match.value.all_query_arguments
                    content {
                    }
                  }

                  dynamic "body" {
                    for_each = field_to_match.value.body
                    content {
                    }
                  }

                  dynamic "method" {
                    for_each = field_to_match.value.method
                    content {
                    }
                  }

                  dynamic "query_string" {
                    for_each = field_to_match.value.query_string
                    content {
                    }
                  }

                  dynamic "single_header" {
                    for_each = field_to_match.value.single_header
                    content {
                      name = single_header.value["name"]
                    }
                  }

                  dynamic "single_query_argument" {
                    for_each = field_to_match.value.single_query_argument
                    content {
                      name = single_query_argument.value["name"]
                    }
                  }

                  dynamic "uri_path" {
                    for_each = field_to_match.value.uri_path
                    content {
                    }
                  }

                }
              }

              dynamic "text_transformation" {
                for_each = sqli_match_statement.value.text_transformation
                content {
                  priority = text_transformation.value["priority"]
                  type     = text_transformation.value["type"]
                }
              }

            }
          }

          dynamic "xss_match_statement" {
            for_each = statement.value.xss_match_statement
            content {

              dynamic "field_to_match" {
                for_each = xss_match_statement.value.field_to_match
                content {

                  dynamic "all_query_arguments" {
                    for_each = field_to_match.value.all_query_arguments
                    content {
                    }
                  }

                  dynamic "body" {
                    for_each = field_to_match.value.body
                    content {
                    }
                  }

                  dynamic "method" {
                    for_each = field_to_match.value.method
                    content {
                    }
                  }

                  dynamic "query_string" {
                    for_each = field_to_match.value.query_string
                    content {
                    }
                  }

                  dynamic "single_header" {
                    for_each = field_to_match.value.single_header
                    content {
                      name = single_header.value["name"]
                    }
                  }

                  dynamic "single_query_argument" {
                    for_each = field_to_match.value.single_query_argument
                    content {
                      name = single_query_argument.value["name"]
                    }
                  }

                  dynamic "uri_path" {
                    for_each = field_to_match.value.uri_path
                    content {
                    }
                  }

                }
              }

              dynamic "text_transformation" {
                for_each = xss_match_statement.value.text_transformation
                content {
                  priority = text_transformation.value["priority"]
                  type     = text_transformation.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "visibility_config" {
        for_each = rule.value.visibility_config
        content {
          cloudwatch_metrics_enabled = visibility_config.value["cloudwatch_metrics_enabled"]
          metric_name                = visibility_config.value["metric_name"]
          sampled_requests_enabled   = visibility_config.value["sampled_requests_enabled"]
        }
      }

    }
  }

  dynamic "visibility_config" {
    for_each = var.visibility_config
    content {
      cloudwatch_metrics_enabled = visibility_config.value["cloudwatch_metrics_enabled"]
      metric_name                = visibility_config.value["metric_name"]
      sampled_requests_enabled   = visibility_config.value["sampled_requests_enabled"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_wafv2_rule_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafv2_rule_group.this.id
}

output "lock_token" {
  description = "returns a string"
  value       = aws_wafv2_rule_group.this.lock_token
}

output "this" {
  value = aws_wafv2_rule_group.this
}
```

[top](#index)