# Project Z

## Overview

Project Z is a cutting-edge lending platform within the decentralized finance (DeFi) ecosystem, built on the unique capabilities of the Move programming language. This blockchain-based platform is designed to enhance lending and borrowing services by providing a secure, transparent, and efficient framework. Utilizing Move allows Project Zenith to leverage advanced smart contract functionalities and safety features, addressing common challenges in the DeFi lending space, such as high collateral requirements and the scarcity of available lending assets. Project Z aims to revolutionize access to financial services, enabling global users to engage in lending activities without traditional financial intermediaries, through competitive interest rates, a user-centric interface, and a sophisticated risk assessment model.

## Audit Summary

This report outlines the findings from a comprehensive security audit conducted for **Project Z**. The audit targeted the project's smart contract suite with the objective of identifying and mitigating potential vulnerabilities, thereby strengthening the security and robustness of the project's blockchain infrastructure.

## Findings Summary

The audit revealed findings categorized under critical and high severity levels. Recommendations for remediation are provided to address these vulnerabilities effectively.

### Vulnerabilities Overview

| ID       | Title                              | Impact                                                                                                       | Severity | Status    |
|----------|------------------------------------|--------------------------------------------------------------------------------------------------------------|----------|-----------|
| VUL-001  | Critical Access Control in `common_config.move` | **Critical Impact**: Unrestricted access to `resource_signer` function poses significant security risk. | Critical | Resolved  |
| VUL-002  | Improper Reward Calculations in `reward_distributor.move` | **High Impact**: Inaccurate reward calculations leading to incorrect token earnings distribution. | High     | Resolved  |

### Finding Count by Severity

- **Critical Severity**: 1
- **High Severity**: 1
