# Welcome to The GoBears NFTs 💎

![](https://github.com/GoBears/nft-minting-app/blob/main/logo-blob.png)

All the code in these repos was created and explained by HashLips & Ali Solanki on their respective YouTube channels.

Hashlips ->https://www.youtube.com/c/HashLipsNFT
Ali Solanki - >https://www.youtube.com/channel/UCgzz4Kd1YpzxJOkrhf5U_7A

Please visit GoBears NFTs Links Below.

[🐦 Twitter](https://twitter.com/GoBearsClub)

[ℹ️ Website](https://GoBears.Club/)

# GoBears NFTs minting dapp 🔥

This repo provides a nice and easy way for linking an existing NFT smart contract to this minting dapp. There are two ways of using this repo, you can go the simple route or the more complex one.

The simple route is so simple, all you need to do is download the build folder on the release page and change the configuration to fit your needs. (Follow the video for a walk through).

The more complex route allows you to add additional functionality if you are comfortable with coding in react.js. (Follow the below instructions for a walk through).

## Installation 🛠️

If you are cloning the project then run this first, otherwise you can download the source code on the release page and skip this step.

```sh
git clone https://github.com/GoBears/mint.git
```

Make sure you have node.js installed so you can use npm, then run:

```sh
npm install
```

## Usage ℹ️

In order to make use of this dapp, all you need to do is change the configurations to point to your smart contract as well as update the images and theme file.

For the most part all the changes will be in the `public` folder.

To link up your existing smart contract, go to the `public/config/config.json` file and update the following fields to fit your smart contract, network and marketplace details. The cost field should be in wei.

Note: this dapp is designed to work with the intended NFT smart contract, that only takes one parameter in the mint function "mintAmount". But you can change that in the App.js file if you need to use a smart contract that takes 2 params.

```json
{
  "CONTRACT_ADDRESS": "0x8213674Dd9ec9ea709bB9DF02BF0D7E34fFFf849",
  "SCAN_LINK": "https://explorer.gochain.io/addr/0x8213674Dd9ec9ea709bB9DF02BF0D7E34fFFf849/",
  "NETWORK": {
    "NAME": "GoChain",
    "SYMBOL": "GO",
    "ID": 60
  },
  "NFT_NAME": "GoBearsClub",
  "SYMBOL": "GBC",
  "MAX_SUPPLY": 10000,
  "WEI_COST": 75000000000000000,
  "DISPLAY_COST": 0.075,
  "GAS_LIMIT": 210000,
  "MARKETPLACE": "Zeromint",
  "MARKETPLACE_LINK": "https://zeromint.com/collections/KWBKjP7UlmZeoZAX-WASv",
  "SHOW_BACKGROUND": true
}
```

Make sure you copy the contract ABI from remix and paste it in the `public/config/abi.json` file.
(follow the youtube video if you struggle with this part).

Now you will need to create and change 2 images and a gif in the `public/config/images` folder, `bg.png`, `example.gif` and `logo.png`.

Next change the theme colors to your liking in the `public/config/theme.css` file.

```css
:root {
  --primary: #ebc908;
  --primary-text: #1a1a1a;
  --secondary: #ff1dec;
  --secondary-text: #ffffff;
  --accent: #ffffff;
  --accent-text: #000000;
}
```

Now you will need to create and change the `public/favicon.ico`, `public/logo192.png`, and
`public/logo512.png` to your brand images.

Remember to update the title and description the `public/index.html` file

```html
<title>GoBears NFTs</title>
<meta name="description" content="Mint your GoBears NFTs" />
```

Also remember to update the short_name and name fields in the `public/manifest.json` file

```json
{
  "short_name": "GBC",
  "name": "GoBearsClub"
}
```

After all the changes you can run.

```sh
npm run start
```

Or create the build if you are ready to deploy.

```sh
npm run build
```

Now you can host the contents of the build folder on a server.

That's it! you're done.
