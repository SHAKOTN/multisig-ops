## [Payload PR - BIP-XXX](https://github.com/BalancerMaxis/multisig-ops/pull/YYY)

## Background
The [v3 Weighted Pool Factory](https://github.com/balancer-labs/balancer-v2-monorepo/tree/master/pkg/deployments/tasks/20230206-weighted-pool-v3) and the [v3 Composable Stable Pool Factory](https://github.com/balancer-labs/balancer-v2-monorepo/tree/master/pkg/deployments/tasks//20230206-composable-stable-pool-v3) where deployed to fix reentrancy issue described [here](https://forum.balancer.fi/t/reentrancy-vulnerability-scope-expanded/4345).  Some initial "wire-up" of permissions is required to bring them into standard function.  This BIP lays out these changes and requests permission to apply them.

## English Specification

The transaction details were generated by [this script](https://github.com/BalancerMaxis/multisig-ops/blob/main/tools/python/gen_add_permissions_payload.py) with inputs and outputs in [this directory](https://github.com/BalancerMaxis/multisig-ops/tree/staging/BIPs/BIP-XXX)

The following files can be found both linked below and in the payload PR linked above:

| Filename                                                                                                                             | Description of Contents                                                                                                              |
|--------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| [inputs.json](https://github.com/BalancerMaxis/multisig-ops/blob/staging/BIPs/BIP-XXX/inputs.json)                                   | The inputs to the script mapping functions and deployments to target addresses that can execute them.                                |
| [results_address_sorted.md](https://github.com/BalancerMaxis/multisig-ops/blob/staging/BIPs/BIP-XXX/results_address_sorted.md)       | The resulting changes printed in a table sorted by target chain and target address. (to easily understand permisisons granted)       |
| [results_deployment_sorted.md](https://github.com/BalancerMaxis/multisig-ops/blob/staging/BIPs/BIP-XXX/results_deployment_sorted.md) | The resulting changes printed in a table sorted by target chain and target deployment. (for verification against action ids)         |
| [function_descriptions.md](https://github.com/BalancerMaxis/multisig-ops/blob/staging/BIPs/BIP-XXX/function_descriptions.md)         | A table that describes what each function that is being granted privileged access to allows.                                         |                                                                                                                                             |
| [`chainname`.json](https://github.com/BalancerMaxis/multisig-ops/tree/staging/BIPs/BIP-XXX/)                                         | For each change with changes, a transaction builder json named after said chain exists to apply the changes described in the tables. |

_More information about the various Balancer Multisigs and their functions can be found in the [multisig-ops repo](https://github.com/BalancerMaxis/multisig-ops/blob/staging/multisigs.md)_

# Specification

As described in the payload json, the authorizer will be called to grant the roles as described.  

The change can be reviewed by the below by comparing the [results_deployment_sorted.md](https://github.com/BalancerMaxis/multisig-ops/tree/staging/BIPs/BIP-183/results_deployment_sorted.md) file to the source of truth,  which should match the order found in the source of truth for actionIds on the [balancer-v2-monorepo](https://github.com/balancer-labs/balancer-v2-monorepo/tree/master/pkg/deployments/action-ids).

For record, the contents of [results_address_sorted.md](https://github.com/BalancerMaxis/multisig-ops/tree/staging/BIPs/BIP-XXX/results_address_sorted.md) are printed here:


ADDRESS_SORTED_MD_TABLE

## Risk Assessment
This BIP is routine operation for provisioning a new factory.  The new factories are themselves a risk mitigation.


## References

[Monorepo Deployment Addresses](https://github.com/balancer-labs/balancer-v2-monorepo/tree/master/pkg/deployments)
