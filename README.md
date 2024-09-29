# Defi-Empire-A-Simple-DeFI-Kingdom-Clone

## Project Description

This project is designed to teach you how to create your own custom subnet using the Avalanche SubnetEVM. You will learn how to deploy this subnet to the local network and then deploy your own contracts to the custom subnet.


## Steps to Run the Project

### Using Remix IDE and Terminal (Easier Way)

1. **Install Avalanche CLI**
   - Install `avalanche-cli` on your UNIX system. Follow the guide [here](https://docs.avax.network/tooling/cli-guides/install-avalanche-cli).
   - To call the avalanche binary from anywhere, you'll need to add it to your system path. If you installed the binary into the default location, you can run the following snippet to add it to your path.
   - In a terminal, run:
     ```bash
     export PATH=~/bin:$PATH
     ``` 

To add it to your path permanently, add an export command to your shell initialization script. If you run bash, use .bashrc. If you run zsh, use .zshrc.

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
     RPC URL:           http://127.0.0.1:9650/ext/bc/2Jz8iH5KWAeYeutjeR7e2ymnyhTd8fvUB4bmsJ2PWLHnriQDcD/rpc
     Funded address:    0x8db97C7cEcE249c2b98bDC0226Cc4C2A57BF52FC with 1000000 (10^18) - private key: 56289e99c94b6912bfc12adc093c9b51124f0dc54ac7a766b2bc5ccf558d8027
     Funded address:    0xe5aAa2A447e1D00D239ecDFad391ee669eF891Bd with 600 (10^18)
     Network name:      akshit
     Chain ID:          234
     Currency Symbol:   ADI
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

- Metacrafter Akshit G Rana

## License

This project is licensed under the MIT License.
