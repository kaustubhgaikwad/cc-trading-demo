# An Ethereum based Carbon Trading Platform

This project aims to demonstrate the trade and consumption of carbon credits on blockchain by using smart contracts to track the origin and path of carbon credits starting from issuance by the Certificate Authority and ending at consumption/retirement.

## Installation instructions

Install python3

In the root folder run the following command (initialize your virtual environment if you want to before this step)

`python -m pip install -r dependencies.txt`

Deploy the smart contract on remix with 'Web3 Provider' option selected and then replace the contract's ABI in app/contract_abi.py

Also replace the corresponding addresses at the start of app/routes.py

The above project has been tested with Ganache. Carefully modify the code in app/routes.py if you want to switch to a different Ethereum test client(such as Infuria)

Remember to update your dependencies.txt file before pushing your update in case you install modules. Use the following command:

`python -m pip freeze > dependencies.txt`

Also run the following command after every pull in order to update your local dependencies

`python -m pip install -r dependencies.txt`

Create `app/contract_abi.py` and paste the abi of your compiled contract's ABI as follows

`abi = """ YOUR ABI HERE """`

Change the contract address, abi and port in `app/templates/requests.html`

Change user_store.json to include the correct wallet addresses.

Clear tx_history.json, purchase_request_store.json, and data_store.json files. 

Create a file called `app/config.py` and insert the following data in it(Added to prevent constant changing of testing params after every pull)

```python
CONTRACT_ADDR = 'YOUR_CONTRACT_ADDRESS'
WALLET_PRIVATE_KEY = 'PRIVATE_KEY_OF_CA'
WALLET_ADDRESS = 'WALLET_ADDRESS_OF_ABOVE_PRIVATE_KEY'
```

## TO-DO List
- [x] When the buy button is clicked, the page reloads to an empty page. Also, the buy page doesn't store state information i.e. a consumer can buy the same CC multiple times. [Benita] 
- [x] Mention the total CC owned by a user under the username [Benita]
- [ ] Updating notifications tab eg. when purchase of CC has been approved/rejected, when CC has been generated by UNFDCCC for you, etc. [Sanidhya]
- [x] Make a page for 'My Profile' tab eg. ability to upload a profile picture, update personal/company information, etc. [Yash]
- [x] Add functionality to the 'Message' tab or just remove it if not needed. [Yash]
- [ ] Add functionaity to the 'Settings' tab or just remove it if not needed. []
- [x] Add a button to the Home page to access the global transaction history. [Benita]
- [x] Add functionaity to the 'Help' tab or just remove it if not needed. [Kaustubh]
- [x] Add an 'About Us' section. []
- [ ] Retiring CC [Sanidhya]
- [x] Registration page [Benita]
- [ ] Home page with stats and graphs [Mrinal, Benita]
