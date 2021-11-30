This is a vanilla JavaScript example how to use Web3modal with different  wallet providers.

The purpose of this example is how to connect a cryptocurrency wallet
to a website that is build on traditional HTML technologies and does not
use any modern JavaScript framework. Uses cases would include:
static HTML sites, WordPress, content management systems,
tutorials and education.

The example works with

* In-browser wallets (MetaMask, Opera, Brave),

* Mobile wallets through QR code scanning (WalletConnect)

* Account-based wallets (Fortmatic, others)

The code uses simple unprocessed in-browser JavaScript.
Dependencies, like the Web3Modal library itself,
are loaded over Unpkg CDN. The code is extensively
commented and short.

# Usage 
Edit your example.js file and change `const contractAddress= "YOUR_NFT_CONTRACT_ADDRESS"`.  
Edit `const ABI` variable with the declaration of your own functions from your contract you want to call.  
Ex: 
```  
const Abi = [  
  // Some details about the token  
  "function symbol() view returns (string)",  

  // Mint Nft function  
  "function mint(uint amount) view returns (string)",  

  // Get the account balance  
  "function balanceOf(address) view returns (uint)",  

  // Check totalSupply of tokens  
  "function totalSupply() view returns (uint)",  
];  
```   

# Web3 wallets and HTTPS hosting limitations

Because of limitations how wallet operate within a web browser
and web security,
you should not run this example, or any Web3modal code,
out of your file system or insecure HTTP protocol
(even using localhost).

The APIs of different wallet providers
may fail in funny and obscure way.
MetaMask does not even show up if you load it over `file://`
protocol.

The easiest way to get local HTTPS development
is to use [https-localhost](https://github.com/daquinoaldo/https-localhost).

Assuming you have a working Node environment set up on a UNIX
system you can do:

`npm i -g --only=prod https-localhost`  
`sudo serve .`  

... in the folder of index.html file.

Then you can visit https://localhost to open the example.

