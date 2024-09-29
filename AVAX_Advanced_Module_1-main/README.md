# AVAX_Advanced_Module_1

## Project Description

This project is designed to teach you how to create your own custom subnet using the Avalanche SubnetEVM. You will learn how to deploy this subnet to the local network and then deploy your own contracts to the custom subnet.

## Video Walkthrough
https://www.loom.com/share/bcc76b763c7d4134a992b01765cd4fbe?sid=ea120afa-bc9e-4a34-9585-eef65a754bb6

## Steps to Run the Project

### Using Remix IDE and Terminal (Easier Way)

1. **Install Avalanche CLI**
   - Install `avalanche-cli` on your UNIX system. Follow the guide [here](https://docs.avax.network/tooling/cli-guides/install-avalanche-cli).

2. **Copy and Test Contracts**
   - Copy `ERC20.sol` and `Vault.sol` from this repository.
   - Paste them into the Remix IDE at [remix.ethereum.org](https://remix.ethereum.org) and test them locally if desired.

3. **Install MetaMask Extension**
   - Install the MetaMask browser extension and create an account.

4. **Create Your Subnet**
   - In a terminal, run:
     ```bash
     avalanche subnet create <your-subnet-name>
     ```
   - Follow the prompts, choosing default options if unsure. For the chain ID, provide a unique positive integer that isn't already used by major blockchains (e.g., 1 for Ethereum). Enter a token symbol when prompted.

5. **Deploy Your Subnet**
   - Run the following command:
     ```bash
     avalanche subnet deploy <your-subnet-name>
     ```
   - Choose "local network" for deployment.

6. **Output Interpretation**
   - The command output will include details such as:
     ```
     RPC URL:           http://127.0.0.1:9650/ext/bc/25LfFJ8UxCMYtj3gMVXSTddRHcbKrsDF4ySe5hx6bu2etwQyzS/rpc
     Funded address:    0x9EfeD1ce512B6c23a838bb34B80154183e8262aB with 1000000 (10^18) - private key: 5843e5dac1fff94f5425ff511d2bde6f42527a7489fcc8b9404aa96075510cea
     Funded address:    0xe705E1C5d619f11c26F851cdAD7BA4C7Eb89bf4f with 600 (10^18)
     Network name:      customSubnet
     Chain ID:          12345
     Currency Symbol:   LNXEDU
     ```

7. **Add Custom Network in MetaMask**
   - Use the details from the output of the last command to add a custom network in MetaMask.

8. **Add Funded Account in MetaMask**
   - Add an account using the provided private key from the output.

9. **Deploy Contracts in Remix**
   - In Remix IDE, select "Injected Web3" as the environment.
   - Deploy `ERC20.sol` first.
   - Then deploy `Vault.sol`, using the deployed address of `erc20.sol` as the constructor parameter.

10. **Mint and Deposit Tokens**
    - Mint some tokens to your address using the `mint` function in `ERC20.sol`.
    - Deposit some tokens and receive shares in return using `Vault.sol`.

## Contributors

- Metacrafter Om Satapathy (Twitter: [@OmSatapathy4](https://twitter.com/OmSatapathy4))

## License

This project is licensed under the MIT License.
