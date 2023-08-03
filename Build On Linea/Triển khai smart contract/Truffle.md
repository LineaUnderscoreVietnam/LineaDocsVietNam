# Truffle

Trong hướng dẫn này, chúng ta sẽ hướng dẫn cách tạo một dự án Truffle cơ bản và triển khai hợp đồng mã thông báo.

Đây là video hướng dẫn:
https://youtu.be/p0nFsVVvNvQ

## Điều kiện cần thiết

Trước khi bắt đầu, hãy đảm bảo bạn đã:
1. [Cài đặt ví](https://github.com/LineaVietNam/LineaDocsVietNam/blob/main/Use%20Linea/C%C3%A0i%20%C4%91%E1%BA%B7t%20v%C3%AD.md)
2. [Nạp tiền vào tài khoản của bạn với Linea ETH ]()
3. [Đã cài đặt Truffle bằng quy trình cài đặt được hướng dẫn ở đây](https://trufflesuite.com/docs/truffle/how-to/install/)

## Tạo 1 project Truffle

Để tạo một dự án Truffle , hãy chạy:
```sh
truffle init linea-tutorial
```
Thay đổi vào thư mục mới:
```sh
cd linea-tutorial
```
## Hãy bắt đầu viết hợp đồng thông minh

Tạo hợp đồng thông minh của bạn trong thư mục hợp đồng bằng cách tạo một tệp mới _Token.sol_ hoặc gọi_ truffle create contract Token_. Sau đó, thêm đoạn mã sau:

```js
pragma solidity 0.8.17;

// SPDX-License-Identifier: MIT

contract Token {
  string public name = "My Token";
  string public symbol = "MTK";
  uint8 public decimals = 18;
  uint256 public totalSupply = 100000000;

  mapping (address => uint256) public balances;
  address public owner;

  constructor() {
    owner = msg.sender;
    balances[owner] = totalSupply;
  }

  function transfer(address recipient, uint256 amount) public {
    require(balances[msg.sender] >= amount, "Insufficient balance.");
    balances[msg.sender] -= amount;
    balances[recipient] += amount;
  }
}
```

> ## Lưu ý : KHÔNG SỬ DỤNG MÃ HỢP ĐỒNG NÀY TRONG SẢN XUẤT Hợp đồng trên là dành cho mục đích thử nghiệm và chưa được kiểm toán.

Bạn có thể kiểm tra xem nó có biên dịch hay không bằng cách chạy _truffle compile_ từ thư mục gốc.

## Viết một migration script 

Để cho Truffle biết cách thức và thứ tự mà chúng ta muốn triển khai các hợp đồng thông minh của mình, chúng ta cần viết một tập lệnh migration . Tạo **1_deploy_token.js** trong thư mục **migrations** và thêm đoạn mã sau:

```js
const Token = artifacts.require("Token");

module.exports = function (deployer) {
  deployer.deploy(Token);
};
```
## Triển khai hợp đồng của bạn

Truffle cho phép bạn triển khai thông qua [Bảng điều khiển Truffle](https://docs.linea.build/build-on-linea/quickstart/deploy-smart-contract/truffle#truffle-dashboard) bằng ví MetaMask của bạn!

## Triển khai lên Mainnet

Sẽ cập nhật sau

### Bảng điều khiển Truffle

[Bảng điều khiển Truffle](https://docs.linea.build/build-on-linea/quickstart/deploy-smart-contract/truffle#truffle-dashboard) cho phép bạn từ bỏ việc lưu các khóa riêng của mình cục bộ, thay vào đó kết nối với ví MetaMask của bạn để triển khai. Để triển khai với Truffle Dashboard, bạn cần:

1. Chạy <code>bảng điều khiển truffle</code> trong thiết bị đầu cuối của bạn, thao tác này sẽ mở một cửa sổ trên cổng <code>24012</code>.
2. Điều hướng đến <code>localhost:24012</code> trong trình duyệt của bạn. Vui lòng đảm bảo rằng Bảng điều khiển được kết nối với mạng thử nghiệm Linea bằng cách kết nối ví MetaMask của bạn với Linea. Để tham khảo, ID mạng thử nghiệm Linea là <code>59140</code>.
![image](https://github.com/LineaVietNam/LineaDocsVietNam/assets/35452526/cfac3ff3-88a2-462c-9eab-fe207905c82c)
3. Chạy <code>truffle migrate --network dashboard</code> trong một terminal riêng biệt.
4. Điều hướng trở lại <code>localhost:24012</code>. Bạn sẽ thấy lời nhắc yêu cầu bạn xác nhận việc triển khai. Nhấp vào **Confirm**.
![image](https://github.com/LineaVietNam/LineaDocsVietNam/assets/35452526/49115a8f-7a53-4c16-ba61-dbfbb12d0fc6)

### truffle-config.js

Bạn có thể triển khai với Truffle bằng dòng lệnh, bằng cách chỉ định Linea trong <code>truffle-config.js</code>. Để làm như vậy, bạn cần phải:
1. Tạo một tệp <code>.env</code> trong thư mục gốc bằng cách ghi nhớ ví của bạn.
   ```sh
   MNEMONIC=<MNEMONIC>
   ```
  > ##### CẢNH BÁO SỰ NGUY HIỂM 
  > Vui lòng không check khóa của bạn vào trong source control. Chúng tôi khuyên bạn nên thêm <code>.env</code> vào <code>.gitignore</code> của mình
2. Tải xuống <code>dotenv</code> và <code>@truffle/hdwallet-provider</code>
```sh
npm i -D dotenv
npm i -D @truffle/hdwallet-provider
```
3. Thêm testnet Linea vào tệp <code>truffle-config.js</code> của bạn:
```js
require("dotenv").config();
const { MNEMONIC } = process.env;

const HDWalletProvider = require("@truffle/hdwallet-provider");

module.exports = {
  networks: {
    linea: {
      provider: () => {
        return new HDWalletProvider(
          MNEMONIC,
          `https://rpc.goerli.linea.build/`,
        );
      },
      network_id: "59140",
    },
  },
  // ... rest of truffle-config.js
};
```
4. Gọi <code>truffle migrate --network linea</code> từ CLI. Đầu ra của bạn sẽ trông giống như sau:
```sh
Compiling your contracts...
===========================
> Everything is up to date, there is nothing to compile.

Starting migrations...
======================
> Network name:    'linea'
> Network id:      59140
> Block gas limit: 30000000 (0x1c9c380)

1_deploy_token.js
=================

  Deploying 'Token'
  -----------------
  > transaction hash:    0x412d58eaf4cc387fe1efa52b105f6fadac36db934b1617d04eaefc1947197525
  > Blocks: 0            Seconds: 0
  > contract address:    0x33b4D321Fc300E4f402820052EFA0958272D2AE5
  > block number:        143419
  > block timestamp:     1677366505
  > account:             YOUR_ACCOUNT_NUMBER
  > balance:             0.088400819995522296
  > gas used:            639672 (0x9c2b8)
  > gas price:           2.500000007 gwei
  > value sent:          0 ETH
  > total cost:          0.001599180004477704 ETH

  > Saving artifacts
  -------------------------------------
  > Total cost:     0.001599180004477704 ETH

Summary
=======
> Total deployments:   1
> Final cost:          0.001599180004477704 ETH
``` -->
```
Tiếp theo, bạn có thể tùy chọn xác minh hợp đồng của mình trên mạng.

> Bạn có thể gặp phải giới hạn tốc độ nếu đang kết nối qua điểm cuối công cộng. Nếu dapp của bạn cần quyền truy cập nút Infura đầy đủ, hãy mở một vé hỗ trợ [tại đây](https://support.infura.io/hc/en-us/articles/15116941373979)
