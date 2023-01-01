# Cashu JS

⚠️ __Don't be reckless:__ This project is in early development, it does however work with real sats! Always use amounts you don't mind loosing.

Cashu Wallet JS is a JavaScript library written in Typescript.

Wallet Features:

[x] connect to mint (load keys)
[x] request minting tokens
[x] minting tokens
[] sending tokens (get encoded token for chosen value)
[] melting tokens
[] ...

## Usage

```javascript
import { CashuMint } from "../../../dist/lib/es6/CashuMint";
import { CashuWallet } from "../../../dist/lib/es6/CashuWallet";

const mint = new CashuMint("{MINT_HOST}","{/path/to/api/root/}, {MINT_PORT}")
const keys = await mint.getKeys()
const wallet = new CashuWallet(keys,mint)

const {pr, hash} = await wallet.requestMint(200)

//pay this LN invoice
console.log(pr)

async function invoiceHasBeenPaid() {
const proofs = await wallet.requestTokens(200,hash)
//Encoded proofs can be spent at the mint
const encoded = wallet.getEncodedProofs(proofs)
console.log(encoded)
}

```

## Contribute

Contributions are very welcome.

If you want to contribute, please open an Issue or a PR. 