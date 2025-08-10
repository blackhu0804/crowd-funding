# crowd-funding

使用 remix 构建了一个基于以太坊的去中心化众筹平台智能合约项目。

## 项目概述

本项目实现了一个完整的众筹系统，包含众筹合约和众筹工厂合约，允许用户创建和参与众筹活动。

## 项目结构

```
├── contracts/           # 智能合约文件
│   ├── Crowdfunding.sol        # 众筹合约
│   ├── CrowdfundingFactory.sol  # 众筹工厂合约
│   └── ...              # 其他示例合约
├── scripts/             # 部署脚本
│   ├── deploy_with_ethers.ts    # 使用 ethers.js 部署
│   ├── deploy_with_web3.ts      # 使用 web3.js 部署
│   ├── ethers-lib.ts           # ethers.js 工具库
│   └── web3-lib.ts             # web3.js 工具库
├── tests/               # 测试文件
├── artifacts/           # 编译后的合约文件
└── .states/            # 状态文件
```

## 主要合约

### Crowdfunding.sol
- 单个众筹项目合约
- 支持资金筹集、退款、提现等功能
- 包含项目状态管理

### CrowdfundingFactory.sol
- 众筹工厂合约
- 用于创建和管理多个众筹项目
- 提供项目查询和统计功能

## 快速开始

### 前置要求
- Remix IDE 或本地开发环境
- MetaMask 钱包
- 测试网 ETH（如 Sepolia 测试网）

### 编译合约
1. 在 Remix IDE 中打开合约文件
2. 选择合适的 Solidity 编译器版本
3. 编译 [contracts/Crowdfunding.sol](contracts/Crowdfunding.sol) 和 [contracts/CrowdfundingFactory.sol](contracts/CrowdfundingFactory.sol)

### 部署合约

使用 ethers.js 部署：
```bash
# 在 Remix IDE 中右键点击 scripts/deploy_with_ethers.ts 选择 'Run'
```

使用 web3.js 部署：
```bash
# 在 Remix IDE 中右键点击 scripts/deploy_with_web3.ts 选择 'Run'
```

### 运行测试
```bash
# 在 Remix IDE 中运行测试文件
```

## 功能特性

- ✅ 创建众筹项目
- ✅ 设置筹资目标和截止时间
- ✅ 投资者参与众筹
- ✅ 项目方提取资金
- ✅ 众筹失败时退款
- ✅ 项目状态跟踪
- ✅ 工厂模式管理多个项目

## 使用说明

### 创建众筹项目
1. 部署 CrowdfundingFactory 合约
2. 调用 `createCrowdfunding()` 方法创建新的众筹项目
3. 设置筹资目标、截止时间等参数

### 参与众筹
1. 连接钱包
2. 选择要投资的项目
3. 发送 ETH 到众筹合约地址

### 项目管理
- 项目创建者可以在达到目标后提取资金
- 投资者可以在项目失败时申请退款
- 查看项目状态和进度

## 开发注意事项

- 合约编译前请确保 Solidity 版本兼容
- 部署时请注意 gas 费用设置
- 测试环境建议使用测试网络
- 生产环境部署前请进行充分的安全审计
