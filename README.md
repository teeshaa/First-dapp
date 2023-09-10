# Deploy Your First Dapp using Spheron!🚀

Welcome to the Dappathon Season 2! In this hands-on guide, we'll walk you through the process of deploying your first decentralized application (Dapp) using Spheron. Follow the steps below to get started.

# Here are some resources : 
## Spheron 
- [Spheron Docs](https://docs.spheron.network/)
- [web deployment link](https://app.spheron.network/#/login)
- [Spheron CLI link](https://www.npmjs.com/package/@spheron/cli)
- [Spheron SDK](https://github.com/spheronFdn/sdk)

## Step 1 : 
- ### Make a new Repo(You can Choose whatever name you want)
- ### Select the option (Add README file)
- ### upload your file (you can refer the step 3 if you haven't created the code)

## Step 2 : 
- ### Add Sepolia Testnet to your metamask.
      - Network Name : Sepolia test network
      - New RPC URL : https://sepolia.infura.io/v3/
      - Chain ID : 11155111
      - Currency Symbol : SepoliaETH
      - Block explorer URL : https://sepolia.etherscan.io
- ### Get Free test ethers : https://sepoliafaucet.com/  


## Step 3 :
- ### Checkout this CODE for Today's Session : 

- ### HTML div : 
```
<div>
      <h1>This is my dApp!</h1>
      <p>Here we can set or get the mood:</p>
      <label for="mood">Input Mood:</label> <br />
      <input type="text" id="mood" />

      <button onclick="getMood()">Get Mood</button>
      <button onclick="setMood()">Set Mood</button>
      <p id="showMood"></p>
    </div>
```

- ### CSS :
  ```
  <style>
      body {
        text-align: center;
        font-family: Arial, Helvetica, sans-serif;
      }

      div {
        width: 20%;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
      }

      button {
        width: 100%;
        margin: 10px 0px 5px 0px;
      }
    </style>
  ```
- ### Ethers.js CDN :
  ```
  <script
      src="https://cdn.ethers.io/lib/ethers-5.7.2.umd.min.js"
      type="application/javascript"
    ></script>
  ```
- ### Ethers.js Code :
  ```
  <script>
      const MoodContractAddress = "<input_Contract_Address>";
      const MoodContractABI = [
        {
          "inputs": [
            {
              "internalType": "string",
              "name": "_mood",
              "type": "string",
            },
          ],
          "name": "setMood",
          "outputs": [],
          "stateMutability": "nonpayable",
          "type": "function",
        },
        {
          "inputs": [],
          "name": "getMood",
          "outputs": [
            {
              "internalType": "string",
              "name": "",
              "type": "string",
            },
          ],
          "stateMutability": "view",
          "type": "function",
        },
      ];

      let MoodContract = undefined;
      let signer = undefined;

      const provider = new ethers.providers.Web3Provider(
        window.ethereum,
        "sepolia"
      );
      provider.send("eth_requestAccounts", []).then(() => {
        provider.listAccounts().then((accounts) => {
          signer = provider.getSigner(accounts[0]);

          MoodContract = new ethers.Contract(
            MoodContractAddress,
            MoodContractABI,
            signer
          );
        });
      });

      async function getMood() {
        const mood = await MoodContract.getMood();

        document.getElementById("showMood").innerText = `Your Mood: ${mood}`;
        console.log(mood);
      }

      async function setMood() {
        const mood = document.getElementById("mood").value;
        await MoodContract.setMood(mood);
      }
    </script>
  ```
## FULL CODE : [repo](input_repo_link)

# Deploy On Spheron : 
## Complete the following steps : 
- visit [spheron](https://app.spheron.network/#/login)
- Click on new Project
- Select Your Repository
- Select a protocol(you can choose IPFS)
- For framework, select No Framework - Simple Javascript app
- Click on Deploy
- After that test whether your Dapp is working or not(by clicking on preview deployment)
- And its Done! You have just Deployed your first Dapp using Spheron!!!

# Submissions
### Once you've successfully deployed your Dapp, it's time to showcase your work! Please submit your Dapp's GitHub repository and live site link in the following format:

[Kirtiraj Thakor](github_link)
