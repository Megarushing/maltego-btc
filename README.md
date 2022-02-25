## Maltego BTC

Set of Maltego transforms written in Go for Bitcoin addresses/wallets investigation. Based on [walletexplorer.com](https://www.walletexplorer.com/) API.

### Installation

Requirements:
 - Maltego 4.0 or higher
 - Go 1.8+

Pre-Installation:
- Install Maltego in your computer https://www.maltego.com/ce-registration/
- Install Blockchain.info Transform by Paterva in the Transform Hub of your maltego

Installation:
- Download binary from https://github.com/Megarushing/maltego-btc/releases and save it in `/usr/local/bin/` on mac, or in Windows `C:\maltego-btc\`. E.g: `sudo cp maltego-btc /usr/local/bin/`
- In the Mac Terminal do `sudo chmod +x /usr/local/bin/maltego-btc`

OR To Compile from sources:
- Install GoLang
- Do `go install github.com/Megarushing/maltego-btc@latest`

Setting up:
- Download [maltego-btc.mtz] (https://github.com/Megarushing/maltego-btc/raw/main/maltego-btc.mtz)
- In Maltego go to Import | Export > Import Config
- Point to the downloaded file and import all transforms, entities and icons
- Important: In the Transform Manager, find the imported transforms and **Edit** each Transform starting with **BTC**, under command line include your path to maltego-btc executable, this is usually `/usr/local/bin/maltego-btc` or `(User Folder)/go/bin/maltego-btc` when compiled from sources.

<img width="1173" alt="image" src="https://user-images.githubusercontent.com/2642709/155597886-88a872aa-213b-4f5e-80db-762ff7b0b0f3.png">


### Config options

This application generates a `maltego-btc.conf` file under `$HOME/Library/Application Support/maltego-btc/` or `C:\Documents and Settings\<User>\Application Data\Local Settings\maltego-btc\` on windows. This can be tweaked if you want to change the settings. Here is a list of config options:

 - ```logfile``` – path to logfile
 - ```cachefile``` – path to cache file
 - ```link_address_color``` – color of arrows from wallets and addresses
 - ```link_wallet_color``` – color of arrows from wallets to wallets
 - ```wallet_max_size``` – max count of transactions to download from api in one go
 - ```cache_addresses``` – max number of addresses to cache
 - ```cache_wallets``` – max number of wallets to cache
 - ```icon_address``` – url to address entity icon
 - ```icon_wallet``` – url to wallet entity icon
 - ```icon_service``` – url to service entity icon
 
### Example Usage

1- Add a bitcoin transaction to your Graph

2- Use the transform: "Blockchain.info > To Destination Addresses" in order to get the addresses it sent to

<img width="1064" alt="image" src="https://user-images.githubusercontent.com/2642709/155611274-933edf81-86a6-4539-9f7d-267bc41bb346.png">

3- Select the destination addresses and convert them into wallets with the transform: "Bitcoin Explorer > Address To Wallet"

<img width="718" alt="image" src="https://user-images.githubusercontent.com/2642709/155611912-111b8e87-6625-4020-bb94-89b0b0d25e7b.png">

4- Verify the destinations, and follow your investigation from there:

<img width="616" alt="image" src="https://user-images.githubusercontent.com/2642709/155612030-1846af3b-f971-41e4-84db-c144bbc8c9e3.png">

5- Try out organizing with the "organic layout" and setting up "ball size by weight" in order to see the amount of funds being moved

<img width="859" alt="image" src="https://user-images.githubusercontent.com/2642709/155612609-803817e8-35fc-44b4-99bd-35e13b89334e.png">


### Screenshots

![Screenshot](assets/screenshot-1.png)
![Screenshot](assets/screenshot-2.png)
![Screenshot](assets/screenshot-3.png)

### Limitations

- Maltego Community Edition has a limitation of only allowing 50 entities per transform, so in case there are too many outputs to a single transaction you may need to run the transform multiple times in order to get all of them, this plugin randomizes the entities it sends every time in order to make this possible.
- In order to not harm the walletexplorer API, the transform may take a long time to get all transactions, a wait time is intentionally applied between requests is applied on large lists, so be patient.

Enjoy!
