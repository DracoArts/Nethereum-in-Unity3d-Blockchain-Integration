
# Welcome to DracoArts

![Logo](https://dracoarts-logo.s3.eu-north-1.amazonaws.com/DracoArts.png)




#  Nethereum in Unity3d  Blockchain Integration
Nethereum is a powerful .NET integration library that serves as a bridge between Unity applications and the Ethereum blockchain, enabling developers to seamlessly incorporate decentralized functionalities into their games and interactive experiences. As a comprehensive toolkit, Nethereum facilitates direct communication with Ethereum clients such as Geth, Parity, and cloud-based services like Infura, allowing for the creation of robust in-game cryptocurrency wallets that empower players with true digital ownership of assets. By leveraging Nethereum's capabilities, developers can implement secure wallet generation, transaction processing, and smart contract interactions entirely within the Unity environment, while maintaining the decentralized principles of blockchain technology. The library supports all fundamental Ethereum operations including key pair generation, transaction signing, balance queries, and gas estimation, while also providing advanced features for working with ERC-20 tokens, ERC-721 NFTs, and custom smart contracts. When integrated properly, Nethereum transforms a traditional Unity game into a Web3-enabled application where players can securely manage their digital assets, participate in play-to-earn economies, and interact with decentralized applications without ever leaving the game environment. The implementation requires careful attention to security practices, particularly around private key management and transaction signing, but when done correctly, it results in a seamless blockchain experience that abstract away the complexities of Ethereum while preserving its decentralized benefits. This integration opens up revolutionary gameplay possibilities including verifiably rare in-game items, player-owned economies, and interoperable assets that can travel across multiple games and platforms, all made possible through Nethereum's reliable connection between Unity's powerful game development framework and Ethereum's decentralized ecosystem.

# Key Features of Nethereum in Unity
## 1. Wallet Creation & Management
- Generate new wallets (public/private key pairs).

- Save wallets as encrypted keystore files (secure storage).

- Import/export wallets using mnemonic phrases (BIP39).
##  Transactions
- Send ETH and tokens (ERC-20, ERC-721).

- Estimate gas fees before sending.

- Sign transactions offline for security.

##  Smart Contract Interaction
- ABI (Application Binary Interface) parsing.

- Call read-only functions (e.g., checking NFT ownership).

- Execute state-changing functions (e.g., minting NFTs).

##  Blockchain Data Queries
- Check wallet balances (ETH & tokens).

- Fetch transaction history.

- Listen to real-time events (e.g., marketplace sales).

# Why Use Nethereum in Unity?
## Cross-Platform Compatibility

- Works on Windows, macOS, Linux, Android, and iOS.

- Integrates with Unity WebGL for browser-based blockchain games.

## Secure Wallet Management

- Generate private keys and wallet addresses.

- Encrypt wallets with keystore files (JSON).

## Sign transactions securely.

- Smart Contract Interaction

- Call functions from Ethereum smart contracts.

- Listen to events (e.g., NFT transfers, token approvals).

## Easy RPC Connection

- Connect to Infura, Alchemy, or local nodes (Geth/Parity).

- Supports Ethereum, Polygon, Binance Smart Chain (BSC), etc.

# Unity Integration Steps
 ## Step 1: Install Nethereum
- Download the Nethereum.Unity package.

- Add it to your Unity project.
## Usage/Examples
Create New Wallet

    public void GenerateNewWallet()
    {
        try
        {
            // Generate 12-word mnemonic
            _currentPhrase = GenerateMnemonic(12);
            
            // Create HD wallet from mnemonic
            var wallet = new Wallet(_currentPhrase, null);
            _currentAccount = wallet.GetAccount(0);
            
            // Display results
            phraseDisplay.text = _currentPhrase;
            currentWalletDisplay.text = $"Address: {_currentAccount.Address}";
            PriavteKeyDisplay.text= $"Private Key: {MaskPrivateKey(_currentAccount.PrivateKey)}";
            Debug.Log(_currentAccount.PrivateKey);
            
                                 
            
            // Save wallet (insecure demo only - use proper secure storage in production)
            PlayerPrefs.SetString("WalletAddress", _currentAccount.Address);
            // Never save private key or phrase in PlayerPrefs in real applications!
            
            walletCreationPanel.SetActive(false);
            walletDisplayPanel.SetActive(true);
            newWalletCreatePanel.SetActive(true);
            statusText.text = "New wallet created successfully!";
        }
        catch (Exception e)
        {
            statusText.text = $"Error: {e.Message}";
            Debug.LogError(e);
        }
    }

Importe  Wallet

    public void ImportWalletFromPrivateKey()
    {
        string privateKey = importPrivateKeyInput.text.Trim();
        
        if (string.IsNullOrEmpty(privateKey))
        {
            statusText.text = "Please enter a private key";
            return;
        }

        try
        {
            // Create account from private key
            _currentAccount = new Account(privateKey);
            _currentPhrase = null; // No phrase for imported wallets
            
            // Display wallet
            currentWalletDisplay.text = $"Wallet Imported!\nAddress: {_currentAccount.Address}";
            
            // Save wallet (insecure demo only)
            PlayerPrefs.SetString("WalletAddress", _currentAccount.Address);
            
            walletImportPanel.SetActive(false);
            walletDisplayPanel.SetActive(true);
            newWalletCreatePanel.SetActive(false);
            statusText.text = "Wallet imported successfully!";
        }
        catch (Exception e)
        {
            statusText.text = $"Invalid private key: {e.Message}";
            Debug.LogError(e);
        }
    }
## Image

## CreateWallet
![](https://github.com/AzharKhemta/Gif-File-images/blob/main/CreateWallet-ezgif.com-video-to-gif-converter.gif?raw=true)

## Import Wallet
![](https://github.com/AzharKhemta/Gif-File-images/blob/main/Import%20Wallet%20Nethereum.gif?raw=true)


## Authors

- [@MirHamzaHasan](https://github.com/MirHamzaHasan)
- [@WebSite](https://mirhamzahasan.com)


## 🔗 Links

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/mir-hamza-hasan/posts/?feedView=all/)
## Documentation

[Nethereum:](https://docs.nethereum.com/en/latest/unity3d-introduction/)




## Tech Stack
**Client:** Unity,C#

**Plugin:** Nethereum



