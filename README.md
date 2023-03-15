# RPC Push Transaction Using CORDA

To create an RPC push transaction using Corda on a VPS SSH Ubuntu 20, you will need to follow these steps:

1. Install Node.js: Run the following commands to install Node.js and npm:
```
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```

2. Clone Ineryjs
```
git clone https://github.com/inery-blockchain/ineryjs
```
```
cd ineryjs
npm install
```
3. Create a new directory for your project and navigate into it:
```
mkdir my-project
```
```
cd my-project
npm init -y
```
4. Install the required packages:
```
npm install $HOME/ineryjs dotenv
```
5. Create a new file called index.js and paste your smart contract code into it.
```
nano index.j
```
6. Set environment variables: Set the following environment variables in a .env file:
```
NODE_URL=http://localhost:10000
PRIV_KEY=<private-key>
ACCOUNT=<account-name>
```
Replace "<private-key>" with your private key and "<account-name>" with the name of your account.

7. Update the code to use the `rpc.send` function instead of the `console.log` function to push the transaction to the blockchain.
```
async function createData() {
  try {
    const result = await rpc.send({
      actions: [api.with(account).as(account).create(id, account, data)]
    })
    console.log(result.processed.action_traces[0].act.name)
    console.log(result.processed.action_traces[0].console)
    console.log(result.processed.action_traces[0])
  } catch (error) {
    console.error(error)
  }
}
```
8. Save the file and run the following command to start the script:
```
node index.js
```
This should execute the four functions `createData()`, `readData()`, `updateData()`, and `deleteData()` and push the transactions to the blockchain using RPC.

Note that you may need to configure your firewall settings to allow incoming and outgoing traffic on the relevant ports to ensure that the RPC requests are successfully sent and received.
