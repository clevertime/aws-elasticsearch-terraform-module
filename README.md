# aws-elasticsearch-terraform-module
terraform module to create aws elasticsearch cluster
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12.9 |
| aws | >= 2.60.0 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 2.60.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| access\_policies | IAM policy document specifying the access policies for the domain | `string` | `""` | no |
| advanced\_options | Key-value string pairs to specify advanced configuration options. Note that the values for these configuration options must be strings (wrapped in quotes) or they may be wrong and cause a perpetual diff, causing Terraform to want to recreate your Elasticsearch domain on every apply | `map(string)` | `{}` | no |
| cluster\_config | Cluster configuration of the domain | `map` | `{}` | no |
| cluster\_config\_availability\_zone\_count | Number of Availability Zones for the domain to use with | `number` | `3` | no |
| cluster\_config\_dedicated\_master\_count | Number of dedicated master nodes in the cluster | `number` | `3` | no |
| cluster\_config\_dedicated\_master\_enabled | Indicates whether dedicated master nodes are enabled for the cluster | `bool` | `true` | no |
| cluster\_config\_dedicated\_master\_type | Instance type of the dedicated master nodes in the cluster | `string` | `"r5.large.elasticsearch"` | no |
| cluster\_config\_instance\_count | Number of instances in the cluster | `number` | `3` | no |
| cluster\_config\_instance\_type | Instance type of data nodes in the cluster | `string` | `"r5.large.elasticsearch"` | no |
| cluster\_config\_zone\_awareness\_enabled | Indicates whether zone awareness is enabled. To enable awareness with three Availability Zones | `bool` | `false` | no |
| cognito\_options | Options for Amazon Cognito Authentication for Kibana | `map` | `{}` | no |
| cognito\_options\_enabled | Specifies whether Amazon Cognito authentication with Kibana is enabled or not | `bool` | `false` | no |
| cognito\_options\_identity\_pool\_id | ID of the Cognito Identity Pool to use | `string` | `""` | no |
| cognito\_options\_role\_arn | ARN of the IAM role that has the AmazonESCognitoAccess policy attached | `string` | `""` | no |
| cognito\_options\_user\_pool\_id | ID of the Cognito User Pool to use | `string` | `""` | no |
| domain\_name | Name of the domain | `string` | n/a | yes |
| ebs\_enabled | Whether EBS volumes are attached to data nodes in the domain | `bool` | `true` | no |
| ebs\_options | EBS related options, may be required based on chosen instance size | `map` | `{}` | no |
| ebs\_options\_iops | The baseline input/output (I/O) performance of EBS volumes attached to data nodes. Applicable only for the Provisioned IOPS EBS volume type | `number` | `0` | no |
| ebs\_options\_volume\_size | The size of EBS volumes attached to data nodes (in GB). Required if ebs\_enabled is set to true | `number` | `10` | no |
| ebs\_options\_volume\_type | The type of EBS volumes attached to data nodes | `string` | `"gp2"` | no |
| elasticsearch\_version | The version of Elasticsearch to deploy. | `string` | `"7.1"` | no |
| encrypt\_at\_rest | Encrypt at rest options. Only available for certain instance types | `map` | `{}` | no |
| encrypt\_at\_rest\_enabled | Whether to enable encryption at rest | `bool` | `true` | no |
| encrypt\_at\_rest\_kms\_key\_id | The KMS key id to encrypt the Elasticsearch domain with. If not specified then it defaults to using the aws/es service KMS key | `string` | `"alias/aws/es"` | no |
| log\_publishing\_options | Options for publishing slow logs to CloudWatch Logs | `map` | `{}` | no |
| log\_publishing\_options\_cloudwatch\_log\_group\_arn | iARN of the Cloudwatch log group to which log needs to be published | `string` | `""` | no |
| log\_publishing\_options\_enabled | Specifies whether given log publishing option is enabled or not | `bool` | `true` | no |
| log\_publishing\_options\_log\_type | A type of Elasticsearch log. Valid values: INDEX\_SLOW\_LOGS, SEARCH\_SLOW\_LOGS, ES\_APPLICATION\_LOGS | `string` | `"INDEX_SLOW_LOGS"` | no |
| node\_to\_node\_encryption | Node-to-node encryption options | `map` | `{}` | no |
| node\_to\_node\_encryption\_enabled | Whether to enable node-to-node encryption | `bool` | `true` | no |
| snapshot\_options | Snapshot related options | `map` | `{}` | no |
| snapshot\_options\_automated\_snapshot\_start\_hour | Hour during which the service takes an automated daily snapshot of the indices in the domain | `number` | `0` | no |
| tags | A mapping of tags to assign to the resource | `map` | `{}` | no |
| timeouts | Timeouts map. | `map` | `{}` | no |
| timeouts\_update | How long to wait for updates. | `string` | `null` | no |
| vpc\_options | VPC related options, see below. Adding or removing this configuration forces a new resource | `map` | `{}` | no |
| vpc\_options\_security\_group\_ids | List of VPC Security Group IDs to be applied to the Elasticsearch domain endpoints. If omitted, the default Security Group for the VPC will be used | `list` | `[]` | no |
| vpc\_options\_subnet\_ids | List of VPC Subnet IDs for the Elasticsearch domain endpoints to be created in | `list` | `[]` | no |

## Outputs

No output.

