#Infrastructure #IaC #Service 

- Tool that lets you create, update, or delete cloud services and infrastructure
- Uses templates
- Written with YAML or JSON

# Template
### AWSTemplateFormatVersion
- Not mandatory
### Description
- Give a description to the template, what it may do, etc.
- Must immediately follow the `AWSTemplateFormatVersion` if one exists

### Metadata
- Controls how different things in the template are presented in the Console UI

### Parameters
- Optional
- Add fields
- Default values
### Mappings
- Optional
- Allows to create LUT (Look Up Tables).

### Conditions
- Allow decision making based on parameter conditions, env variables, etc
### Resources
- All templates have a list of resources, at least 1
- Tells cloud formation what to do
- If resources are added, then CloudFormation creates those resources
- If resources are modified, then CloudFormation updates those resources
- [AWS resource and property types reference - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
### Outputs
- Once a template is finished, the template could present a set of outputs 
# Logical Resource
Logical Resources are what are inside CloudFormation Templates
- Type: What type of resource to create
- Properties to describe and modify the logical resource

# Stack
- Contains all logical resources that the template tells it to contain
- Living and active representation of the template
- There can be 1 or more stacks created by CloudFormation
- For every logical resource, there is a physical resource