# The 6529 Gradient Collection

### Contracts  
**Mainnet** `0x0c58ef43ff3032005e472cb5709f8908acb00205`  
**Rinkeby** `0xa423b2c73584312d3f166f827d2d09f0eb63efa5`

### Gateway [IPFS]  
`https://6529.mypinata.cloud`  

### Metadata  
`https://6529.mypinata.cloud/ipfs/QmVEAjABzeCG7nSQCc5T6E25ENt8UdgC6JGDTSRzkkTygu/{token_id}`

### OpenSea  

`https://opensea.io/collection/6529-gradient`

### Reading on-chain data
```python
import os
import json
import dotenv
dotenv.load_dotenv()

# Infura credentials (or other Web3 provider)
from web3 import Web3
INFURA_ENDPOINT = "https://mainnet.infura.io/v3/{}".format(os.getenv("INFURA_KEY"))
ADDRESS = "0x0C58Ef43fF3032005e472cB5709f8908aCb00205"
ABI = json.loads("0x0C58Ef43fF3032005e472cB5709f8908aCb00205.json")

# Initialize connection
w3 = Web3(Web3.HTTPProvider(INFURA_ENDPOINT))
contract = w3.eth.contract(address=ADDRESS, abi=ABI)

# Retrieve on-chain data
token_id = 0
data = contract.functions.tokenData(token_id).call()
print(data)
```