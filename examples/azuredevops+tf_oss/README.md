# Azure DevOps Server + Terraform OSS Example

This example shows how to configure AFT with Azure DevOps Server as the VCS provider and Terraform OSS as the Terraform distribution.

## Important Note

**Azure DevOps Server support is currently pending implementation by AWS in CodeConnections.** This example and the AFT framework have been prepared to support Azure DevOps once it becomes officially available.

## Prerequisites

- Azure DevOps Server instance
- Appropriate network connectivity between AFT and Azure DevOps Server
- Repository structure following AFT requirements

## Configuration

The key differences when using Azure DevOps Server:

1. Set `vcs_provider = "azuredevops"`
2. Provide your Azure DevOps Server URL in `azuredevops_url`
3. Use Azure DevOps repository naming format: `Organization/Project/_git/RepositoryName`

## Repository Naming Convention

Azure DevOps repositories should be specified in the format:
```
Organization/Project/_git/RepositoryName
```

For example:
- `ExampleOrg/ExampleProject/_git/aft-account-request`
- `ExampleOrg/ExampleProject/_git/aft-global-customizations`

## Network Requirements

If deploying AFT with VPC enabled (`aft_enable_vpc = true`), ensure your VPC has appropriate connectivity to your Azure DevOps Server instance.

## Next Steps

Once AWS adds Azure DevOps Server support to CodeConnections:

1. Update the provider type in the AFT module source
2. Create the CodeConnections connection to your Azure DevOps Server
3. Deploy AFT with your Azure DevOps repositories

## Related Documentation

- [AFT Guide](https://docs.aws.amazon.com/controltower/latest/userguide/aft-overview.html)
- [AWS CodeConnections Documentation](https://docs.aws.amazon.com/dtconsole/latest/userguide/connections.html)