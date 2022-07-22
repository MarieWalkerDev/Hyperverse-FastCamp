# Assignment 1

In this exercise we are assuming that you already have installed and know how to use the following:
- An IDE like [VS Code](https://code.visualstudio.com/download) which is one of the most popular ones
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/en/) - use 14.0.0 or higher
- [Yarn](https://classic.yarnpkg.com/en/docs/install#mac-stable)

### Now lets get this app going
- Go to [docs.hyperverse.dev](docs.hyperverse.dev)
- On the left panel click on the `Build web3 apps` drop down
- Select `Environment Setup`

*There are two ways of getting the app going*
1. Create from scratch using [create-next-app](https://docs.hyperverse.dev/basics/environment#using-create-next-app), or 
2. Create using sample apps already built using [Hyperverse Monorepo](https://docs.hyperverse.dev/basics/environment#using-the-hyperverse-monorepo) 

*In this example we will be using option #2*

- In your terminal clone the repo Hyperverse Monorepo by typing
`git clone https://github.com/decentology/hyperverse-mono`
- There are three modules you can choose from:
    1. Ethereum
    2. Flow
    3. Algorand
- In this example we will navigate to the Ethereum module
- In your terminal navigate to `cd hyperverse-mono/apps/ethereum/tribes`
- Install project dependencies by typing `yarn` in your terminal
- Run the development server by typing `yarn dev` in your terminal
- On your browser go to `http://localhost:3000`


### Now the fun part
*All functionalities from the ERC721 module will be listed on the localhost and they are ready and available for you to play around with*
- First you want to connect your wallet
- On the upper right corner click on the `Connect Wallet` button
- Select your preferred wallet. For this example we will use a wallet from MetaMask
- Select the wallet you want to use, then `Next` and `Connect`
- You will know that you are connected by navigating to the top right and you will be able to see your wallet address
- Now we need to create an instance of the ERC721 token - **_this will be your contract with your data_**
- Under the `Token Factory Functions` category, go to `New Instance` and click `Create Instance`
- Enter a token name *(a twitter username)*
- Enter a token symbol *(initials)*
- Click on `Create Instance`
- Confirm the transaction in your wallet popup


### Lets update some code
- First we need to update the `tenantId` with the correct address - **_The `tenantId` points to the wallet address which created the instance and this is where it is pulling the data from_**
- Open the ERC721 folder in the IDE at `hyperverse-mono/apps/ethereum/ERC721`
- Under `pages` open the `_app.tsx` file
- Scroll down to `function MyApp` and change the address for `tenantId` to the address the instance was created with
- Save the file
- Go back to `http://localhost:3000` and refresh the page

### Lets mint an NFT
- Under the `Token Factory Functions` category, go to `Get Proxy Token` and click on `Get Proxy` - **_this will return us our address_**
- Now we will mint the NFT
- Under the `Tenant Owner Functions` category, go to `Mint and click on `Mint`
- For the `Receiver` you will need to paste an address where it is going to - **_this is who do you want to send this to_**
- Choose a file image - **_this will be put on IPFS_**
- Click `Mint`
- Confirm the transaction in your wallet popup
- Under the `Token Functions` category, go to `Balance Of` and click `Get Balance Of` paste the address - **_this will show you how many tokens you have_**