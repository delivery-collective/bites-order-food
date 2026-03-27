# Bites Order Food -- Claude Code Plugin

Order food from local restaurants conversationally in Claude Code. Search restaurants, browse menus, customize items, build a cart, and get a checkout link -- all without leaving the terminal. Powered by [Bites](https://withbites.com).

## Prerequisites

1. **Claude Code** installed

That's it. The plugin automatically connects to the Bites MCP server -- no manual server setup required.

## Installation

```bash
claude plugin add delivery-collective/bites-order-food
```

## Usage

In Claude Code, type:

```
/order-food
```

The assistant walks you through:

1. **Find a restaurant** -- search by name, cuisine, dietary needs, or location
2. **Browse the menu** -- view categories, items, prices, and DoorDash savings
3. **Customize items** -- pick sizes, toppings, and other modifiers conversationally
4. **Review your cart** -- see itemized breakdown with delivery fee, tax, and tip
5. **Check out** -- get a link to complete payment in your browser

## Authentication

The plugin supports two modes:

- **Authenticated (OAuth2):** See rewards balances, past orders, and favorites
- **Guest mode:** Search, browse, and place orders without logging in

## How It Works

The plugin is a Claude Code skill that orchestrates the Bites MCP server tools:

| Tool | Purpose |
|------|---------|
| `searchRestaurants` | Find restaurants by query, cuisine, dietary options, rating |
| `getRestaurant` | Get menu items, categories, rewards, promotions |
| `getItemModifiers` | Get customization options for a menu item |
| `getAutoFilledCartItem` | Build a cart item with nested modifiers auto-filled |
| `createOrder` | Place the order and get a checkout URL |

Payment is completed in the browser via the Bites storefront -- no payment info is handled in the terminal.

## License

MIT
