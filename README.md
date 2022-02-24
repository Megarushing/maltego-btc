## Maltego BTC

Set of Maltego transforms written in Go for Bitcoin addresses/wallets investigation. Based on [walletexplorer.com](https://www.walletexplorer.com/) API.

### Installation

Requirements:
 - Maltego 4.0 or higher
 - Go 1.8+

Installation:
- Install Maltego in your computer https://www.maltego.com/ce-registration/
- Install Blockchain.info Transform by Paterva in the Transform Hub of your maltego
- Download binary from https://github.com/Megarushing/maltego-btc/releases and save it in /usr/local/bin/
- In the terminal do `chmod +x /usr/local/bin/maltego-btc`

OR To Compile from sources
- Install GoLang
- Do `go install github.com/Megarushing/maltego-btc@latest`

Setting up:
- Download [maltego-btc.mtz] (https://github.com/Megarushing/maltego-btc/raw/master/maltego-btc.mtz)
- In Maltego go to Import | Export > Import Config
- Point to the downloaded file and import all transforms, entities and icons
- Important: Edit each Transform BTC command line to include your path to maltego-btc, this is usually `(User Folder)/go/bin/maltego-btc`

<img width="1173" alt="image" src="https://user-images.githubusercontent.com/2642709/155597886-88a872aa-213b-4f5e-80db-762ff7b0b0f3.png">


Recommended:
- I recommend also installing maltegos library standard blockchain.com transform to use alongside

### Config options

Edit config.json and re-run installation commands. List of config options:

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
 
### Screenshots

![Screenshot](assets/screenshot-1.png)
![Screenshot](assets/screenshot-2.png)
![Screenshot](assets/screenshot-3.png)

Enjoy responsibly!
