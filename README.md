# TR Markets - FiveM Market System

A fully-featured market/shop system for FiveM servers with multiple market types, modern NUI interface, and comprehensive payment options.

## Features

- **Multiple Preconfigured Market Types**
  - 24/7 Markets
  - LTD Gas Stations
  - Liquor Stores
  - Black Market (illegal shops)

- **Modern Shopping Interface**
  - Vue.js powered NUI for smooth interactions
  - Category browsing system
  - Search functionality
  - Real-time cart management
  - Professional tablet-style UI

- **Payment System**
  - Cash payments
  - Bank transfers
  - VIP coins (premium currency)
  - Separate currency for illegal markets (dirty money)

- **Server Features**
  - Configurable item pricing
  - Discord webhook logging for all purchases
  - VIP item support with custom pricing
  - Dynamic ped spawning at market locations
  - Map blips for easy navigation
  - Multiple location support per market type

- **Customization**
  - Easy configuration of shops, items, and prices
  - Custom market logos
  - Category icons using Font Awesome
  - Editable ped models and blip sprites

## Requirements

- ESX Framework
- ox_target
- ox_lib
- oxmysql
- ox_inventory

## Installation

1. Download and place the resource in your resources folder
2. Add to your server.cfg: `ensure tr_markets`
3. Configure the markets in `config.lua`:
   - Set Discord webhooks for each market type
   - Customize items, prices, and locations
   - Adjust ped models and blip sprites if desired
4. Restart your server or use `refresh` command

## Configuration

### Adding Custom Items

In `config.lua`, locate the market type and add items to categories:

```lua
{
    name = "burger",
    label = "Burger",
    price = 4,
    isVip = false
}
```

For VIP items:

```lua
{
    name = "exclusive_item",
    label = "Exclusive Item",
    price = 5000,
    isVip = true,
    vipPrice = 100
}
```

### Market Types

- **regular**: Standard 24/7 shops
- **ltd**: Gas station convenience stores
- **liquor**: Alcohol and beverage stores
- **illegal**: Black market for restricted items
- **custom**: Custom market types can be created

### Discord Webhooks

Update webhook URLs in the configuration:

```lua
Config.Webhooks = {
    ['regular'] = "YOUR_WEBHOOK_URL",
    ['liquor'] = "YOUR_WEBHOOK_URL",
    ['ltd'] = "YOUR_WEBHOOK_URL",
    ['illegal'] = "YOUR_WEBHOOK_URL"
}
```

All purchases are logged with player info, items, and payment method.

## VIP System

The script supports a VIP coin system for premium items. Configure your VIP callback:

```lua
Config.GetVipCoinsCallback = function(source, cb)
    -- Return player's VIP coins
    cb(vipCoinAmount)
end
```

If not using VIP, the callback can remain empty.

## Usage

- Use ox_target on peds to open the shop
- Browse categories or search for items
- Add items to cart and adjust quantities
- Select payment method (cash or bank, except black market)
- Complete your purchase

## Support

For issues or feature requests, contact me on my discord server: https://discord.gg/aGkWMRKEaB.
