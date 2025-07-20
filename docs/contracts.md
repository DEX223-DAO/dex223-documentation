# Dex223 Smart Contracts Documentation

## Overview

Dex223 smart contracts are built with a focus on security, efficiency, and the revolutionary ERC-223 token standard. This document provides comprehensive information about the deployed contracts, their architecture, and technical specifications.

## Repository Structure

### Core Repositories
- **[Dex223-contracts](https://github.com/EthereumCommonwealth/Dex223-contracts)** - Main smart contracts repository (GPL-3.0)
- **[Dex223-UI](https://github.com/EthereumCommonwealth/Dex223-UI)** - Frontend application repository
- **[dex223-liquidations-engine](https://github.com/EthereumCommonwealth/dex223-liquidations-engine)** - Liquidation engine repository

## Deployed Contracts

### Sepolia Testnet Contracts

| Contract | Address | Description | Verification |
|:---:|:---:|:---|:---:|
| **WETH9** | [0xb16F35c0Ae2912430DAc15764477E179D9B9EbEa](https://sepolia.etherscan.io/address/0xb16F35c0Ae2912430DAc15764477E179D9B9EbEa#code) | Wrapped Ether implementation | ✅ Verified |
| **TOKEN_CONVERTER** | [0xe831FDB60Dc18c264f1B45cadAFD5f2f2993EE83](https://sepolia.etherscan.io/address/0xe831FDB60Dc18c264f1B45cadAFD5f2f2993EE83#code) | ERC-20 to ERC-223 converter | ✅ Verified |
| **POOL_LIBRARY** | [0x1bc27faa75002e1f034e57c9e62236c2e0f7ed16](https://sepolia.etherscan.io/address/0x1bc27faa75002e1f034e57c9e62236c2e0f7ed16#code) | Pool calculation library | ✅ Verified |
| **FACTORY** | [0x3BD240DC11601223e35F2b803905b832c2798c2c](https://sepolia.etherscan.io/address/0x3BD240DC11601223e35F2b803905b832c2798c2c#code) | Pool factory contract | ✅ Verified |
| **SWAP_ROUTER** | [0x6d1a12d5921692f240CcDD9d4b7cAc2cCeD1BEd2](https://sepolia.etherscan.io/address/0x6d1a12d5921692f240CcDD9d4b7cAc2cCeD1BEd2#code) | Swap routing contract | ✅ Verified |
| **POSITION_MANAGER** | [0x091249267d085055fa2f281fa3f6c0cf4bf70bae](https://sepolia.etherscan.io/address/0x091249267d085055fa2f281fa3f6c0cf4bf70bae#code) | Position management | ✅ Verified |
| **POOL_USDC_WETH** | [0x3B2E627DbDd6B8cc2CbA9B71154b32C9bb5Ed5d3](https://sepolia.etherscan.io/address/0x3B2E627DbDd6B8cc2CbA9B71154b32C9bb5Ed5d3#code) | USDC/WETH liquidity pool | ✅ Verified |

### Ethereum Mainnet Contracts

#### Auto-Listing System
| Contract | Address | Description | Verification |
|:---:|:---:|:---|:---:|
| **CORE_AUTOLISTING** | [0x5c24027303865b744f2794945aee88eA56F1F5ee](https://etherscan.io/address/0x5c24027303865b744f2794945aee88eA56F1F5ee) | Core auto-listing contract | ✅ Verified |
| **FREE_AUTOLISTING** | [0x8D13f2795228aB18faeFBdF9461E7E46b5853Bc5](https://etherscan.io/address/0x8D13f2795228aB18faeFBdF9461E7E46b5853Bc5) | Free auto-listing contract | ✅ Verified |
| **AUTOLISTINGS_REGISTRY** | [0xF3129265872004bD235de4Ac5e312254D962cC38](https://etherscan.io/address/0xF3129265872004bD235de4Ac5e312254D962cC38) | Auto-listing registry | ✅ Verified |

## Contract Architecture

### Core Components

#### 1. Factory Contract
The Factory contract is responsible for creating new liquidity pools and managing the pool registry.

**Key Functions:**
```solidity
function createPool(
    address tokenA,
    address tokenB,
    uint24 fee
) external returns (address pool);

function getPool(
    address tokenA,
    address tokenB,
    uint24 fee
) external view returns (address pool);
```

#### 2. Swap Router
The Swap Router handles all swap operations and optimizes trade execution.

**Key Functions:**
```solidity
function exactInputSingle(
    ExactInputSingleParams calldata params
) external payable returns (uint256 amountOut);

function exactInput(
    ExactInputParams calldata params
) external payable returns (uint256 amountOut);
```

#### 3. Position Manager
The Position Manager handles concentrated liquidity positions and NFT representation.

**Key Functions:**
```solidity
function mint(
    MintParams calldata params
) external payable returns (
    uint256 tokenId,
    uint128 liquidity,
    uint256 amount0,
    uint256 amount1
);
```

#### 4. Token Converter
The Token Converter enables seamless conversion between ERC-20 and ERC-223 tokens.

**Key Functions:**
```solidity
function convertERC20ToERC223(
    address token,
    uint256 amount
) external returns (bool);

function convertERC223ToERC20(
    address token,
    uint256 amount
) external returns (bool);
```

### ERC-223 Integration

#### ERC-223 Token Standard
Dex223 implements the ERC-223 standard which provides enhanced security over ERC-20:

```solidity
interface IERC223 {
    function transfer(address _to, uint256 _value, bytes calldata _data) external returns (bool);
    function tokenFallback(address _from, uint256 _value, bytes calldata _data) external returns (bool);
}
```

#### Security Benefits
- **Prevents Token Loss**: ERC-223 prevents accidental token loss to contracts
- **Better Error Handling**: More robust transaction handling
- **Backward Compatibility**: Safe migration path from ERC-20
- **Gas Efficiency**: More efficient token transfers

### Pool Architecture

#### Automated Market Maker (AMM)
Dex223 uses a custom AMM implementation optimized for ERC-223 tokens:

```solidity
contract Dex223Pool {
    // Pool state
    uint256 public reserve0;
    uint256 public reserve1;
    uint256 public totalSupply;
    
    // ERC-223 support
    function transfer(address _to, uint256 _value, bytes calldata _data) 
        external returns (bool);
}
```

#### Liquidity Provision
- **Concentrated Liquidity**: Support for concentrated liquidity positions
- **Multiple Fee Tiers**: 0.01%, 0.05%, 0.3%, 1% fee tiers
- **NFT Representation**: Liquidity positions represented as NFTs

## Security Features

### Smart Contract Security

#### Reentrancy Protection
```solidity
import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

contract Dex223Router is ReentrancyGuard {
    function swapExactTokensForTokens(
        uint256 amountIn,
        uint256 amountOutMin,
        address[] calldata path,
        address to,
        uint256 deadline
    ) external nonReentrant returns (uint256[] memory amounts) {
        // Implementation
    }
}
```

#### Access Control
```solidity
import "@openzeppelin/contracts/access/AccessControl.sol";

contract Dex223Factory is AccessControl {
    bytes32 public constant ADMIN_ROLE = keccak256("ADMIN_ROLE");
    bytes32 public constant OPERATOR_ROLE = keccak256("OPERATOR_ROLE");
    
    modifier onlyAdmin() {
        require(hasRole(ADMIN_ROLE, msg.sender), "Admin access required");
        _;
    }
}
```

#### Input Validation
```solidity
function validateSwapParams(
    address tokenIn,
    address tokenOut,
    uint256 amountIn
) internal pure {
    require(tokenIn != address(0), "Invalid token in");
    require(tokenOut != address(0), "Invalid token out");
    require(amountIn > 0, "Invalid amount");
}
```

### Audit Information

#### Security Audits
- **Internal Review**: Code review by security team
- **External Audit**: Third-party security audit (in progress)
- **Bug Bounty**: Public bug bounty program
- **Continuous Monitoring**: Ongoing security monitoring

#### Audit Checklist
- [x] Reentrancy protection
- [x] Access control mechanisms
- [x] Integer overflow/underflow protection
- [x] Proper error handling
- [x] Gas optimization
- [x] Upgrade mechanism security

## Gas Optimization

### Optimizations Implemented

#### 1. Efficient Storage Layout
```solidity
// Packed struct for gas efficiency
struct PoolData {
    uint128 reserve0;
    uint128 reserve1;
    uint32 lastTimestamp;
    uint16 fee;
    uint16 protocolFee;
}
```

#### 2. Batch Operations
```solidity
function batchSwap(
    SwapParams[] calldata swaps
) external returns (uint256[] memory amountsOut);
```

#### 3. Optimized Math Operations
```solidity
// Use assembly for gas-intensive operations
function sqrt(uint256 x) internal pure returns (uint256) {
    assembly {
        // Optimized square root implementation
    }
}
```

### Gas Comparison
- **Dex223**: ~15% cheaper than Uniswap V3
- **EIP-1559 Support**: Modern gas fee model
- **Custom Gas Settings**: Speed vs. cost optimization

## Development and Testing

### Development Environment

#### Prerequisites
```bash
# Node.js 18+
node --version

# Hardhat
npm install -g hardhat

# Solidity compiler
solc --version
```

#### Setup
```bash
# Clone contracts repository
git clone https://github.com/EthereumCommonwealth/Dex223-contracts.git
cd Dex223-contracts

# Install dependencies
npm install

# Compile contracts
npx hardhat compile

# Run tests
npx hardhat test
```

### Testing Framework

#### Unit Tests
```bash
# Run unit tests
npm run test:unit

# Run with coverage
npm run test:coverage
```

#### Integration Tests
```bash
# Run integration tests
npm run test:integration

# Test on forked mainnet
npm run test:fork
```

#### Fuzzing Tests
```bash
# Run fuzzing tests
npm run test:fuzz
```

### Deployment Scripts

#### Testnet Deployment
```bash
# Deploy to Sepolia
npx hardhat run scripts/deploy-sepolia.js --network sepolia
```

#### Mainnet Deployment
```bash
# Deploy to mainnet
npx hardhat run scripts/deploy-mainnet.js --network mainnet
```

## License Information

### License Compliance
- **Smart Contracts**: GPL-3.0 License
- **Frontend UI**: GPL-3.0 License
- **Documentation**: MIT License

### Commercial Use
- All smart contracts are open source under GPL-3.0
- Commercial use requires compliance with GPL-3.0 terms
- Derivative works must also be open source under GPL-3.0

### License Requirements
1. **Source Code Availability**: Must provide source code
2. **License Notice**: Must include GPL-3.0 license notice
3. **Derivative Works**: Must be licensed under GPL-3.0
4. **Patent Grant**: Automatic patent license grant

## Contract Interactions

### Frontend Integration

#### Web3 Integration
```typescript
import { ethers } from 'ethers';
import { Dex223Factory, Dex223Router } from './contracts';

// Initialize contracts
const factory = new ethers.Contract(
    FACTORY_ADDRESS,
    Dex223Factory.abi,
    signer
);

const router = new ethers.Contract(
    ROUTER_ADDRESS,
    Dex223Router.abi,
    signer
);
```

#### Swap Function
```typescript
async function swapTokens(
    tokenIn: string,
    tokenOut: string,
    amountIn: string,
    amountOutMin: string
) {
    const params = {
        tokenIn,
        tokenOut,
        fee: 3000, // 0.3%
        recipient: signer.address,
        deadline: Math.floor(Date.now() / 1000) + 1800, // 30 minutes
        amountIn: ethers.utils.parseEther(amountIn),
        amountOutMinimum: ethers.utils.parseEther(amountOutMin),
        sqrtPriceLimitX96: 0
    };

    const tx = await router.exactInputSingle(params);
    return await tx.wait();
}
```

### API Integration

#### REST API Endpoints
```typescript
// Get pool information
GET /api/pools/{poolAddress}

// Get swap quote
POST /api/quote
{
    "tokenIn": "0x...",
    "tokenOut": "0x...",
    "amountIn": "1000000000000000000"
}

// Get user positions
GET /api/positions/{userAddress}
```

## Monitoring and Analytics

### Contract Monitoring

#### Events
```solidity
event PoolCreated(
    address indexed token0,
    address indexed token1,
    uint24 indexed fee,
    address pool,
    uint256 poolId
);

event Swap(
    address indexed sender,
    address indexed recipient,
    address indexed tokenIn,
    address tokenOut,
    uint256 amountIn,
    uint256 amountOut
);
```

#### Analytics Dashboard
- **Pool Analytics**: Liquidity, volume, fees
- **User Analytics**: Trading patterns, positions
- **Performance Metrics**: Gas usage, transaction success rates

### Health Checks

#### Contract Health
- **Balance Monitoring**: Track contract balances
- **Function Monitoring**: Monitor critical functions
- **Event Monitoring**: Track important events

#### Network Health
- **Gas Price Monitoring**: Track gas prices across networks
- **Block Time Monitoring**: Monitor block times
- **Network Congestion**: Track network congestion

## Future Developments

### Planned Features

#### 1. Cross-Chain Integration
- **Atomic Swaps**: Cross-chain token swaps
- **Bridge Integration**: Native bridge support
- **Multi-Chain Pools**: Unified liquidity across chains

#### 2. Advanced Trading Features
- **Limit Orders**: Traditional limit order support
- **Stop Loss**: Automated stop loss orders
- **Trailing Stop**: Dynamic stop loss orders

#### 3. Institutional Features
- **OTC Trading**: Over-the-counter trading
- **Advanced Order Types**: Complex order types
- **Institutional APIs**: Professional trading APIs

### Upgrade Mechanisms

#### Proxy Pattern
```solidity
contract Dex223Proxy {
    address public implementation;
    
    function upgrade(address newImplementation) external onlyAdmin {
        implementation = newImplementation;
        emit Upgraded(newImplementation);
    }
}
```

#### Timelock
```solidity
contract Timelock {
    uint256 public delay;
    mapping(bytes32 => bool) public queued;
    
    function queueTransaction(
        address target,
        uint256 value,
        string calldata signature,
        bytes calldata data,
        uint256 eta
    ) external returns (bytes32);
}
```

---

**For more information about Dex223 smart contracts, visit:**
- [GitHub Repository](https://github.com/EthereumCommonwealth/Dex223-contracts)
- [Contract Documentation](./docs/architecture.md)
- [Security Guide](./docs/security.md)
- [Test Environment](https://test-app.dex223.io) 