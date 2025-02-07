---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "snowflake_masking_policy Resource - terraform-provider-snowflake"
subcategory: ""
description: |-
  
---

# snowflake_masking_policy (Resource)



## Example Usage

```terraform
resource "snowflake_masking_policy" "example_masking_policy" {
  name               = "EXAMPLE_MASKING_POLICY"
  database           = "EXAMPLE_DB"
  schema             = "EXAMPLE_SCHEMA"
  value_data_type    = "string"
  masking_expression = "case when current_role() in ('ANALYST') then val else sha2(val, 512) end"
  return_data_type   = "string"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `database` (String) The database in which to create the masking policy.
- `masking_expression` (String) Specifies the SQL expression that transforms the data.
- `name` (String) Specifies the identifier for the masking policy; must be unique for the database and schema in which the masking policy is created.
- `return_data_type` (String) Specifies the data type to return.
- `schema` (String) The schema in which to create the masking policy.
- `value_data_type` (String) Specifies the data type to mask.

### Optional

- `comment` (String) Specifies a comment for the masking policy.

### Read-Only

- `id` (String) The ID of this resource.
- `qualified_name` (String) Specifies the qualified identifier for the masking policy.

## Import

Import is supported using the following syntax:

```shell
# format is database name | schema name | policy name
terraform import snowflake_masking_policy.example 'dbName|schemaName|policyName'
```
