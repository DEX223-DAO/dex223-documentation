# Dex223 Multi-Chain Configuration

## Overview

Dex223 supports a comprehensive range of **50+ EVM-compatible blockchains** to provide users with maximum flexibility and access to diverse liquidity pools across the entire EVM ecosystem. This document outlines the complete multi-chain architecture and configuration focused exclusively on EVM chains.

## Supported EVM Chains

### Layer 1 Networks

#### Ethereum Ecosystem
- **Ethereum Mainnet** (Chain ID: 1)
  - RPC: `https://eth-mainnet.g.alchemy.com/v2/`
  - Explorer: `https://etherscan.io`
  - Native Token: ETH
  - Gas Optimization: EIP-1559

- **Ethereum Sepolia Testnet** (Chain ID: 11155111)
  - RPC: `https://eth-sepolia.g.alchemy.com/v2/`
  - Explorer: `https://sepolia.etherscan.io`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Binance Smart Chain (BSC)
- **BSC Mainnet** (Chain ID: 56)
  - RPC: `https://bsc-dataseed1.binance.org`
  - Explorer: `https://bscscan.com`
  - Native Token: BNB
  - Gas Optimization: BSC-specific

- **BSC Testnet** (Chain ID: 97)
  - RPC: `https://data-seed-prebsc-1-s1.binance.org:8545`
  - Explorer: `https://testnet.bscscan.com`
  - Native Token: tBNB
  - Purpose: Development & Testing

#### Polygon (MATIC)
- **Polygon Mainnet** (Chain ID: 137)
  - RPC: `https://polygon-rpc.com`
  - Explorer: `https://polygonscan.com`
  - Native Token: MATIC
  - Gas Optimization: Polygon PoS

- **Polygon Mumbai Testnet** (Chain ID: 80001)
  - RPC: `https://rpc-mumbai.maticvigil.com`
  - Explorer: `https://mumbai.polygonscan.com`
  - Native Token: MATIC
  - Purpose: Development & Testing

#### Avalanche (AVAX)
- **Avalanche C-Chain** (Chain ID: 43114)
  - RPC: `https://api.avax.network/ext/bc/C/rpc`
  - Explorer: `https://snowtrace.io`
  - Native Token: AVAX
  - Gas Optimization: Avalanche-specific

- **Avalanche Fuji Testnet** (Chain ID: 43113)
  - RPC: `https://api.avax-test.network/ext/bc/C/rpc`
  - Explorer: `https://testnet.snowtrace.io`
  - Native Token: AVAX
  - Purpose: Development & Testing

#### Fantom (FTM)
- **Fantom Opera** (Chain ID: 250)
  - RPC: `https://rpc.ftm.tools`
  - Explorer: `https://ftmscan.com`
  - Native Token: FTM
  - Gas Optimization: Fantom-specific

- **Fantom Testnet** (Chain ID: 4002)
  - RPC: `https://rpc.testnet.fantom.network`
  - Explorer: `https://testnet.ftmscan.com`
  - Native Token: FTM
  - Purpose: Development & Testing

#### Cronos (CRO)
- **Cronos Mainnet** (Chain ID: 25)
  - RPC: `https://evm.cronos.org`
  - Explorer: `https://cronoscan.com`
  - Native Token: CRO
  - Gas Optimization: Cronos-specific

- **Cronos Testnet** (Chain ID: 338)
  - RPC: `https://evm-t3.cronos.org`
  - Explorer: `https://testnet.cronoscan.com`
  - Native Token: tCRO
  - Purpose: Development & Testing

#### Harmony (ONE)
- **Harmony Mainnet** (Chain ID: 1666600000)
  - RPC: `https://api.harmony.one`
  - Explorer: `https://explorer.harmony.one`
  - Native Token: ONE
  - Gas Optimization: Harmony-specific

- **Harmony Testnet** (Chain ID: 1666700000)
  - RPC: `https://api.s0.b.hmny.io`
  - Explorer: `https://explorer.pops.one`
  - Native Token: ONE
  - Purpose: Development & Testing

#### Celo (CELO)
- **Celo Mainnet** (Chain ID: 42220)
  - RPC: `https://forno.celo.org`
  - Explorer: `https://explorer.celo.org`
  - Native Token: CELO
  - Gas Optimization: Celo-specific

- **Celo Alfajores Testnet** (Chain ID: 44787)
  - RPC: `https://alfajores-forno.celo-testnet.org`
  - Explorer: `https://alfajores-blockscout.celo-testnet.org`
  - Native Token: CELO
  - Purpose: Development & Testing

#### Moonbeam (GLMR)
- **Moonbeam** (Chain ID: 1284)
  - RPC: `https://rpc.api.moonbeam.network`
  - Explorer: `https://moonbeam.moonscan.io`
  - Native Token: GLMR
  - Gas Optimization: Moonbeam-specific

- **Moonbase Alpha** (Chain ID: 1287)
  - RPC: `https://rpc.api.moonbase.moonbeam.network`
  - Explorer: `https://moonbase.moonscan.io`
  - Native Token: DEV
  - Purpose: Development & Testing

#### Moonriver (MOVR)
- **Moonriver** (Chain ID: 1285)
  - RPC: `https://rpc.api.moonriver.moonbeam.network`
  - Explorer: `https://moonriver.moonscan.io`
  - Native Token: MOVR
  - Gas Optimization: Moonriver-specific

#### Astar (ASTR)
- **Astar** (Chain ID: 592)
  - RPC: `https://rpc.astar.network:8545`
  - Explorer: `https://astar.subscan.io`
  - Native Token: ASTR
  - Gas Optimization: Astar-specific

- **Astar Shibuya Testnet** (Chain ID: 81)
  - RPC: `https://rpc.shibuya.astar.network:8545`
  - Explorer: `https://shibuya.subscan.io`
  - Native Token: SBY
  - Purpose: Development & Testing

#### Shiden (SDN)
- **Shiden** (Chain ID: 336)
  - RPC: `https://shiden.api.onfinality.io/public`
  - Explorer: `https://shiden.subscan.io`
  - Native Token: SDN
  - Gas Optimization: Shiden-specific

### Layer 2 Networks

#### Arbitrum
- **Arbitrum One** (Chain ID: 42161)
  - RPC: `https://arb1.arbitrum.io/rpc`
  - Explorer: `https://arbiscan.io`
  - Native Token: ETH
  - Gas Optimization: L2-specific

- **Arbitrum Nova** (Chain ID: 42170)
  - RPC: `https://nova.arbitrum.io/rpc`
  - Explorer: `https://nova.arbiscan.io`
  - Native Token: ETH
  - Gas Optimization: L2-specific

- **Arbitrum Sepolia** (Chain ID: 421614)
  - RPC: `https://sepolia-rollup.arbitrum.io/rpc`
  - Explorer: `https://sepolia.arbiscan.io`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Optimism
- **Optimism** (Chain ID: 10)
  - RPC: `https://mainnet.optimism.io`
  - Explorer: `https://optimistic.etherscan.io`
  - Native Token: ETH
  - Gas Optimization: L2-specific

- **Optimism Sepolia** (Chain ID: 11155420)
  - RPC: `https://sepolia.optimism.io`
  - Explorer: `https://sepolia-optimism.etherscan.io`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Base
- **Base** (Chain ID: 8453)
  - RPC: `https://mainnet.base.org`
  - Explorer: `https://basescan.org`
  - Native Token: ETH
  - Gas Optimization: L2-specific

- **Base Sepolia** (Chain ID: 84532)
  - RPC: `https://sepolia.base.org`
  - Explorer: `https://sepolia.basescan.org`
  - Native Token: ETH
  - Purpose: Development & Testing

#### zkSync Era
- **zkSync Era Mainnet** (Chain ID: 324)
  - RPC: `https://mainnet.era.zksync.io`
  - Explorer: `https://explorer.zksync.io`
  - Native Token: ETH
  - Gas Optimization: ZK-rollup

- **zkSync Era Sepolia** (Chain ID: 280)
  - RPC: `https://sepolia.era.zksync.io`
  - Explorer: `https://sepolia.explorer.zksync.io`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Polygon zkEVM
- **Polygon zkEVM** (Chain ID: 1101)
  - RPC: `https://zkevm-rpc.com`
  - Explorer: `https://zkevm.polygonscan.com`
  - Native Token: ETH
  - Gas Optimization: ZK-rollup

- **Polygon zkEVM Testnet** (Chain ID: 1442)
  - RPC: `https://rpc.public.zkevm-test.net`
  - Explorer: `https://testnet-zkevm.polygonscan.com`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Linea
- **Linea** (Chain ID: 59144)
  - RPC: `https://rpc.linea.build`
  - Explorer: `https://lineascan.build`
  - Native Token: ETH
  - Gas Optimization: L2-specific

- **Linea Sepolia** (Chain ID: 59141)
  - RPC: `https://rpc.sepolia.linea.build`
  - Explorer: `https://sepolia.lineascan.build`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Mantle
- **Mantle** (Chain ID: 5000)
  - RPC: `https://rpc.mantle.xyz`
  - Explorer: `https://explorer.mantle.xyz`
  - Native Token: MNT
  - Gas Optimization: L2-specific

- **Mantle Sepolia** (Chain ID: 5001)
  - RPC: `https://rpc.sepolia.mantle.xyz`
  - Explorer: `https://explorer.sepolia.mantle.xyz`
  - Native Token: MNT
  - Purpose: Development & Testing

#### Scroll
- **Scroll** (Chain ID: 534352)
  - RPC: `https://rpc.scroll.io`
  - Explorer: `https://scrollscan.com`
  - Native Token: ETH
  - Gas Optimization: ZK-rollup

- **Scroll Sepolia** (Chain ID: 534351)
  - RPC: `https://sepolia-rpc.scroll.io`
  - Explorer: `https://sepolia.scrollscan.com`
  - Native Token: ETH
  - Purpose: Development & Testing

#### Immutable X
- **Immutable X** (Chain ID: 1337)
  - RPC: `https://rpc.immutable.com`
  - Explorer: `https://immutascan.io`
  - Native Token: ETH
  - Gas Optimization: L2-specific

#### Loopring
- **Loopring** (Chain ID: 1264)
  - RPC: `https://mainnet.infura.io/v3/`
  - Explorer: `https://explorer.loopring.io`
  - Native Token: ETH
  - Gas Optimization: ZK-rollup

### Sidechains & App-Specific Chains

#### Gnosis Chain (xDAI)
- **Gnosis Chain** (Chain ID: 100)
  - RPC: `https://rpc.gnosischain.com`
  - Explorer: `https://gnosisscan.io`
  - Native Token: XDAI
  - Gas Optimization: PoS-specific

#### Chiliz (CHZ)
- **Chiliz** (Chain ID: 88888)
  - RPC: `https://rpc.chiliz.com`
  - Explorer: `https://explorer.chiliz.com`
  - Native Token: CHZ
  - Gas Optimization: Chiliz-specific

#### Klaytn (KLAY)
- **Klaytn** (Chain ID: 8217)
  - RPC: `https://public-node-api.klaytnapi.com/v1/cypress`
  - Explorer: `https://scope.klaytn.com`
  - Native Token: KLAY
  - Gas Optimization: Klaytn-specific

- **Klaytn Baobab Testnet** (Chain ID: 1001)
  - RPC: `https://public-node-api.klaytnapi.com/v1/baobab`
  - Explorer: `https://baobab.scope.klaytn.com`
  - Native Token: KLAY
  - Purpose: Development & Testing

#### Velas (VLX)
- **Velas** (Chain ID: 106)
  - RPC: `https://evmexplorer.velas.com/rpc`
  - Explorer: `https://evmexplorer.velas.com`
  - Native Token: VLX
  - Gas Optimization: Velas-specific

#### IoTeX (IOTX)
- **IoTeX** (Chain ID: 4689)
  - RPC: `https://babel-api.mainnet.iotex.io`
  - Explorer: `https://iotexscan.io`
  - Native Token: IOTX
  - Gas Optimization: IoTeX-specific

- **IoTeX Testnet** (Chain ID: 4690)
  - RPC: `https://babel-api.testnet.iotex.io`
  - Explorer: `https://testnet.iotexscan.io`
  - Native Token: IOTX
  - Purpose: Development & Testing

#### Oasis (ROSE)
- **Oasis Emerald** (Chain ID: 42262)
  - RPC: `https://emerald.oasis.dev`
  - Explorer: `https://explorer.emerald.oasis.dev`
  - Native Token: ROSE
  - Gas Optimization: Oasis-specific

- **Oasis Testnet** (Chain ID: 42261)
  - RPC: `https://testnet.emerald.oasis.dev`
  - Explorer: `https://testnet.explorer.emerald.oasis.dev`
  - Native Token: ROSE
  - Purpose: Development & Testing

#### Evmos (EVMOS)
- **Evmos** (Chain ID: 9001)
  - RPC: `https://eth.bd.evmos.org:8545`
  - Explorer: `https://escan.live`
  - Native Token: EVMOS
  - Gas Optimization: Evmos-specific

- **Evmos Testnet** (Chain ID: 9000)
  - RPC: `https://eth.bd.evmos.dev:8545`
  - Explorer: `https://testnet.escan.live`
  - Native Token: EVMOS
  - Purpose: Development & Testing

#### Canto (CANTO)
- **Canto** (Chain ID: 7700)
  - RPC: `https://canto.slingshot.finance`
  - Explorer: `https://tuber.build`
  - Native Token: CANTO
  - Gas Optimization: Canto-specific

#### Mantle (MNT)
- **Mantle** (Chain ID: 5000)
  - RPC: `https://rpc.mantle.xyz`
  - Explorer: `https://explorer.mantle.xyz`
  - Native Token: MNT
  - Gas Optimization: Mantle-specific

#### Kava (KAVA)
- **Kava EVM** (Chain ID: 2222)
  - RPC: `https://evm.kava.io`
  - Explorer: `https://kavascan.com`
  - Native Token: KAVA
  - Gas Optimization: Kava-specific

#### OKX Chain (OKT)
- **OKX Chain** (Chain ID: 66)
  - RPC: `https://exchainrpc.okx.org`
  - Explorer: `https://www.oklink.com/okc`
  - Native Token: OKT
  - Gas Optimization: OKX-specific

#### Conflux (CFX)
- **Conflux eSpace** (Chain ID: 1030)
  - RPC: `https://evm.confluxrpc.com`
  - Explorer: `https://evm.confluxscan.io`
  - Native Token: CFX
  - Gas Optimization: Conflux-specific

#### Metis (METIS)
- **Metis** (Chain ID: 1088)
  - RPC: `https://andromeda.metis.io/?owner=1088`
  - Explorer: `https://andromeda-explorer.metis.io`
  - Native Token: METIS
  - Gas Optimization: L2-specific

#### Boba Network (BOBA)
- **Boba Network** (Chain ID: 288)
  - RPC: `https://mainnet.boba.network`
  - Explorer: `https://bobascan.com`
  - Native Token: ETH
  - Gas Optimization: L2-specific

#### Aurora (AURORA)
- **Aurora** (Chain ID: 1313161554)
  - RPC: `https://mainnet.aurora.dev`
  - Explorer: `https://aurorascan.dev`
  - Native Token: ETH
  - Gas Optimization: Aurora-specific

#### Near Protocol (NEAR)
- **Aurora on NEAR** (Chain ID: 1313161554)
  - RPC: `https://mainnet.aurora.dev`
  - Explorer: `https://aurorascan.dev`
  - Native Token: NEAR
  - Gas Optimization: NEAR-specific

## Configuration Implementation

### Chain Configuration TypeScript Interface

```typescript
interface ChainConfig {
  id: number;
  name: string;
  network: string;
  nativeCurrency: {
    name: string;
    symbol: string;
    decimals: number;
  };
  rpcUrls: {
    default: { http: string[] };
    public: { http: string[] };
  };
  blockExplorers: {
    default: { name: string; url: string };
  };
  contracts: {
    multicall3: {
      address: string;
      blockCreated: number;
    };
  };
  gasOptimization: {
    type: 'EIP-1559' | 'L2' | 'ZK-rollup' | 'PoS' | 'Custom';
    maxFeePerGas?: number;
    maxPriorityFeePerGas?: number;
  };
  features: {
    crossChain: boolean;
    aiOptimization: boolean;
    institutional: boolean;
  };
}

interface MultiChainConfig {
  chains: ChainConfig[];
  defaultChain: number;
  supportedChains: number[];
  crossChainBridges: BridgeConfig[];
}
```

### Environment Configuration

```typescript
// lib/chains/config.ts
export const CHAIN_CONFIGS: Record<number, ChainConfig> = {
  1: {
    id: 1,
    name: 'Ethereum',
    network: 'ethereum',
    nativeCurrency: { name: 'Ether', symbol: 'ETH', decimals: 18 },
    rpcUrls: {
      default: { http: ['https://eth-mainnet.g.alchemy.com/v2/'] },
      public: { http: ['https://eth-mainnet.g.alchemy.com/v2/'] }
    },
    blockExplorers: {
      default: { name: 'Etherscan', url: 'https://etherscan.io' }
    },
    contracts: {
      multicall3: {
        address: '0xca11bde05977b3631167028862be2a173976ca11',
        blockCreated: 14353601
      }
    },
    gasOptimization: { type: 'EIP-1559' },
    features: {
      crossChain: true,
      aiOptimization: true,
      institutional: true
    }
  },
  // ... Add all other chains
};
```

### Cross-Chain Bridge Configuration

```typescript
interface BridgeConfig {
  id: string;
  name: string;
  sourceChain: number;
  targetChain: number;
  contractAddress: string;
  supportedTokens: string[];
  fees: {
    percentage: number;
    minimum: number;
    maximum: number;
  };
  estimatedTime: number; // in minutes
  security: {
    audited: boolean;
    insurance: boolean;
    liquidity: number;
  };
}

export const BRIDGE_CONFIGS: BridgeConfig[] = [
  {
    id: 'multichain',
    name: 'Multichain Bridge',
    sourceChain: 1,
    targetChain: 137,
    contractAddress: '0x6f4c9b0b1c0e3e2e1e0d9c8b7a6f5e4d3c2b1a0',
    supportedTokens: ['USDC', 'USDT', 'ETH', 'MATIC'],
    fees: { percentage: 0.1, minimum: 10, maximum: 1000 },
    estimatedTime: 15,
    security: { audited: true, insurance: true, liquidity: 1000000 }
  },
  // ... Add more bridge configurations
];
```

### Gas Optimization Strategy

```typescript
interface GasStrategy {
  chainId: number;
  strategy: 'EIP-1559' | 'Legacy' | 'L2' | 'Custom';
  parameters: {
    maxFeePerGas?: number;
    maxPriorityFeePerGas?: number;
    gasPrice?: number;
    gasLimit?: number;
  };
  fallback: GasStrategy;
}

export const GAS_STRATEGIES: Record<number, GasStrategy> = {
  1: {
    chainId: 1,
    strategy: 'EIP-1559',
    parameters: {
      maxFeePerGas: 50000000000, // 50 gwei
      maxPriorityFeePerGas: 2000000000 // 2 gwei
    },
    fallback: {
      chainId: 1,
      strategy: 'Legacy',
      parameters: { gasPrice: 30000000000 } // 30 gwei
    }
  },
  // ... Add strategies for all chains
};
```

## Cross-Chain Features

### Atomic Swaps
- Cross-chain token swaps without intermediaries
- Time-locked contracts for security
- Multi-hop routing for optimal paths

### Liquidity Aggregation
- Aggregate liquidity from multiple chains
- Smart routing for best execution
- Cross-chain arbitrage opportunities

### Portfolio Management
- Unified portfolio across all chains
- Cross-chain balance tracking
- Performance analytics

### Bridge Integration
- Native bridge support for major chains
- Third-party bridge integration
- Bridge comparison and optimization

## Security Considerations

### Cross-Chain Security
- Bridge risk assessment
- Liquidity verification
- Transaction monitoring
- Fraud detection

### Gas Optimization
- Chain-specific gas strategies
- Dynamic fee adjustment
- Batch transaction support
- MEV protection

### Network Monitoring
- Chain health monitoring
- RPC endpoint redundancy
- Transaction confirmation tracking
- Error handling and recovery

## Performance Optimization

### RPC Management
- Multiple RPC endpoints per chain
- Load balancing and failover
- Rate limiting and caching
- Connection pooling

### Data Synchronization
- Real-time cross-chain data
- Optimistic updates
- Conflict resolution
- State consistency

### User Experience
- Chain switching optimization
- Transaction status tracking
- Cross-chain transaction history
- Unified interface

## Future Enhancements

### Planned Features
- Cross-chain NFT support
- Multi-chain DeFi integrations
- Cross-chain governance
- Advanced bridge protocols

### Emerging Chains
- Layer 3 solutions
- App-specific rollups
- Zero-knowledge proofs
- Privacy-preserving chains

This comprehensive EVM-focused multi-chain configuration ensures Dex223 can support the widest possible range of EVM-compatible blockchains while maintaining optimal performance, security, and user experience across the entire EVM ecosystem. 