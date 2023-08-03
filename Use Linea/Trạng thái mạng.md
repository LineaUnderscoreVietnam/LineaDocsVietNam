# Thông tin mạng và hợp đồng triển khai

## Trạng thái mạng

Bạn có thể tìm hiểu cách điều hướng đến trạng thái mạng Linea [ở đây]()

## Thông tin mạng

### Mainnet
| Tên mạng  | Linea |
| ------------- | ------------- |
| RPC URL  | https://linea-mainnet.infura.io/v3 hoặc qua [Infura](https://support.linea.build/hc/en-us/signin?return_to=https%3A%2F%2Fsupport.linea.build%2Fhc%2Fen-us%2Farticles%2F15752713253147) (được khuyến nghị) |
| Chain ID  | 59144  |
| Currency Symbol | ETH |
|Block Explorer URL| [Lineascan](https://lineascan.build/)|
### Testnet
| Tên mạng  | Linea |
| ------------- | ------------- |
| RPC URL  | https://rpc.goerli.linea.build hoặc qua [Infura](https://support.linea.build/hc/en-us/signin?return_to=https%3A%2F%2Fsupport.linea.build%2Fhc%2Fen-us%2Farticles%2F15752713253147) (được khuyến nghị) |
| Chain ID  | 59140  |
| Currency Symbol | ETH |
|Block Explorer URL| [Lineascan](https://lineascan.build/)|

## Kết nối với Infura

Nếu dapp của bạn đang sử dụng điểm cuối công khai https://rpc.goerli.linea.build, nó có thể gặp phải giới hạn tốc độ. Chúng tôi khuyên bạn nên kết nối với Linea qua Infura bằng các [hướng dẫn này](https://support.linea.build/hc/en-us/articles/15752713253147).

## Hợp đồng triển khai
### Mainnet
| Contract  | Địa chỉ |
| ------------- | ------------- |
| L1 Message Service  | [0xd19d4B5d358258f05D7B411E21A1460D11B0876F](https://etherscan.io/address/0xd19d4B5d358258f05D7B411E21A1460D11B0876F) |
| L2 Message Service  | [0x508Ca82Df566dCD1B0DE8296e70a96332cD644ec](https://lineascan.build/address/0x508Ca82Df566dCD1B0DE8296e70a96332cD644ec)  |
### Testnet
| Contract  | Địa chỉ |
| ------------- | ------------- |
| L1 Message Service  | [0xE87d317eB8dcc9afE24d9f63D6C760e52Bc18A40](https://etherscan.io/address/0xE87d317eB8dcc9afE24d9f63D6C760e52Bc18A40) |
| L2 Message Service  | [0xA59477f7742Ba7d51bb1E487a8540aB339d6801d](https://lineascan.build/address/0xA59477f7742Ba7d51bb1E487a8540aB339d6801d)  |

## Địa chỉ hợp đồng mã thông báo và cầu nối

### Mainnet
Tương lai sẽ có thêm địa chỉ mới...

| **Token**     | **L1** | **Địa chỉ L1** | **Địa chỉ L2** | **Cầu** |
| ------------- | -------------|-------------|-------------|-------------|
|WETH|-|-|0xe5D7C2a44FfDDf6b295A15c148167daaAf5Cf34f|-|

### Testnet
| **Token**     | **L1** | **Địa chỉ L1** | **Địa chỉ L2** | **Cầu** |
| ------------- | -------------|-------------|-------------|-------------|
|ETH|Goerli|0x70BaD09280FD342D02fe64119779BC1f0791BAC2|0xC499a572640B64eA1C8c194c43Bc3E19940719dC|[HOP](https://goerli.hop.exchange/#/send?token=ETH&sourceNetwork=ethereum&destNetwork=linea)|
|USDC|Goerli|0x07865c6e87b9f70255377e024ace6630c1eaa37f|0xf56dc6695cF1f5c364eDEbC7Dc7077ac9B586068|[HOP](https://goerli.hop.exchange/#/send?token=ETH&sourceNetwork=ethereum&destNetwork=linea)|
|DAI|Goerli|0xb93cba7013f4557cDFB590fD152d24Ef4063485f|0x8741Ba6225A6BF91f9D73531A98A89807857a2B3|[HOP](https://goerli.hop.exchange/#/send?token=ETH&sourceNetwork=ethereum&destNetwork=linea)|
|USDT|Goerli|0xfad6367E97217cC51b4cd838Cc086831f81d38C2|0x1990BC6dfe2ef605Bfc08f5A23564dB75642Ad73|[HOP](https://goerli.hop.exchange/#/send?token=ETH&sourceNetwork=ethereum&destNetwork=linea)|
|HOP|Goerli|0x38aF6928BF1Fd6B3c768752e716C49eb8206e20c|0x6F03052743CD99ce1b29265E377e320CD24Eb632|[HOP](https://goerli.hop.exchange/#/send?token=ETH&sourceNetwork=ethereum&destNetwork=linea)|
|BNB|BSC|Mã thông báo gốc|0x5471ea8f739dd37E9B81Be9c5c77754D8AA953E4|[Celer](https://dev-cbridge-v2.netlify.app/97/59140/BNB)|
|BUSD|BSC|0xeb3eb991d39dac92616da64b7c6d5af5ccff1627|0x7d43AABC515C356145049227CeE54B608342c0ad|[Celer](https://dev-cbridge-v2.netlify.app/97/59140/BNB)|
|AVAX|Fuji|Mã thông báo gốc|Multi-chain|[Multichain](https://test.multichain.org/#/router)|
|TUSD|Fuji|0xd00B9BBC6EDC3953Ec502d73E7FA7C59f628d947|0x922D641a426DcFFaeF11680e5358F34d97d112E1|[Multichain](https://test.multichain.org/#/router)|
|EUROe|Fuji|0xA089a21902914C3f3325dBE2334E9B466071E5f1|0xeFAeeE334F0Fd1712f9a8cc375f427D9Cdd40d73|[Multichain](https://test.multichain.org/#/router)|
|MATIC|Mumbai|Mã thông báo gốc|0xcAA61BCAe7D37Fe9C33c0D8671448254eef44D63|[Connext](https://testnet.bridge.connext.network/)|
|UNI|Goerli|0x41E5E6045f91B61AACC99edca0967D518fB44CFB|0x7823E8DCC8bfc23EA3AC899EB86921f90e80F499|[HOP](https://goerli.hop.exchange/#/send?token=ETH&sourceNetwork=ethereum&destNetwork=linea)|
|WETH|-|-|0x2C1b868d6596a18e32E61B901E4060C872647b6C|-|

## Một số mã hợp đồng quan trọng
### Mainnet
Hợp đồng Mainnet sắp ra mắt.

### Testnet
|Mã hợp đồng |
|----------|
|[IBridge.sol](https://docs.linea.build/files/testnet/IBridge.sol)|
|[IL1Bridge.sol](https://docs.linea.build/files/testnet/IL1Bridge.sol)|
|[IMessageService.sol](https://docs.linea.build/files/testnet/IMessageService.sol)|
|[MessageServiceBase.sol](https://docs.linea.build/files/testnet/MessageServiceBase.sol)|
|[TokenBridge.sol](https://docs.linea.build/files/testnet/TokenBridge.sol)|
