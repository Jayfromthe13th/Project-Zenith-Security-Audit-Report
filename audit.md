# Project Zenith: Security Audit Report

## Overview

Project Zenith is a cutting-edge lending platform within the decentralized finance (DeFi) ecosystem, built on the unique capabilities of the Move programming language. This blockchain-based platform is designed to enhance lending and borrowing services by providing a secure, transparent, and efficient framework. Utilizing Move allows Project Zenith to leverage advanced smart contract functionalities and safety features, addressing common challenges in the DeFi lending space, such as high collateral requirements and the scarcity of available lending assets. Project Zenith aims to revolutionize access to financial services, enabling global users to engage in lending activities without traditional financial intermediaries, through competitive interest rates, a user-centric interface, and a sophisticated risk assessment model.



## Audit Summary

This report outlines the findings from a comprehensive security audit conducted for **Project Zenith**. The audit targeted the project's smart contract suite with the objective of identifying and mitigating potential vulnerabilities, thereby strengthening the security and robustness of the project's blockchain infrastructure.

## Findings Summary

The audit revealed findings categorized under critical and high severity levels. Recommendations for remediation are provided to address these vulnerabilities effectively.

### Critical Findings 

#### Critical Access Control in `common_config.move`

- **Description:**  
  The `resource_signer` function in `common_config.move` is crucial for generating, saving, and retrieving resource accounts, which are used for token storage in other modules. This function's unrestricted access poses a significant security risk.

- **Affected Code:**
  ```rust
  public fun resource_signer(seed: vector<u8>): signer acquires ResourceOwnershipCapStore {
      assert!(resource_acc_exists_at(seed), ERROR_SEED);
      let resources = &borrow_global<ResourceOwnershipCapStore>(@LYF).resources;
      account::create_signer_with_capability(&table::borrow(resources, seed).signer_cap)
  }

- **Recommendation:**  
  Limit the `resource_signer` function access exclusively to trusted protocol modules by changing its access level to `friend`.

### High Severity Findings

#### Improper Reward Calculations in `reward_distributor.move`

- **Description:**  
  The `accumulated_gain` function inaccurately calculates token earnings, neglecting contributions to subsequent scales, leading to incorrect reward distributions.
**Affected Code:**
```rust
#[test(account = @0xA)]
fun test_gain(account: &signer) {
    ...
    // Err: Expected 500, actual output is 450
}
```
- **Recommendation:**
Revise the reward calculation logic within accumulated_gain to include all relevant factors, ensuring accurate earnings distribution.




Conclusion
The audit of Project Zenith uncovered critical and high-severity issues requiring immediate attention to protect the project's integrity and user assets. Implementing the recommended changes will significantly enhance the security framework of the project.
