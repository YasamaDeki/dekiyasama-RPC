# RPC Push Transaction Using CORDA

Here are the step-by-step instructions to install Corda and run the RPC push transaction using the smart contract you provided on a VPS SSH Ubuntu 20:

1. Install Java 8: Run the following command to install Java 8 on your VPS:

```
sudo apt install openjdk-8-jdk
```

2. Install Corda: Run the following command to download and install the Corda binaries:
```
wget https://dl.bintray.com/corda/maven/net/corda/corda/4.8/corda-4.8.jar
```

3. Run Corda: Run the following command to start the Corda node:
```
java -jar corda-4.8.jar
```

4. Connect to the Corda node: Once Corda is up and running, you can connect to it from your local machine using SSH port forwarding. Run the following command on your local machine:
```
ssh -L 10000:localhost:10000 user@<vps-ip>
```

5. Install Node.js: Run the following commands to install Node.js and npm:
```
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```
6. Clone Ineryjs
```
git clone https://github.com/inery-blockchain/ineryjs
```
7. Run the following command to install ineryjs:
```
cd ineryjs
npm install
```
8. Set environment variables: Set the following environment variables in a .env file:
```
NODE_URL=http://localhost:10000
PRIV_KEY=<private-key>
ACCOUNT=<account-name>
```
Replace "<private-key>" with your private key and "<account-name>" with the name of your account.

9. Run the script: Run the script you provided using the following command:
```
node <script-name>.js
```
Replace "<script-name>" with the name of your script.

That's it! The script will execute and you should see the output on the console.

```

```

```

```

