---
description: '20% Supply: Lot based auction distribution protocol (custom built)'
---

# auction

### [disclaimer](auction.md#disclaime)

## overview

The largest component of the distribution will occur through an auction contract that was created specifically for the SMOL launch. Similar to the auction mechanic utilized by Hyperliquid for ticker auctions, this contract conducts a lot based Dutch style auction (price decreases with time). When a lot is sold the starting price of the next lot is increased by some multiple.

## how it works

A lot auction begins at a starting price that decreases linearly at a set rate until it reaches a minimum price floor. When a lot is purchased, the starting price of the next lot increases by a factor applied to the sale price and begins decreasing again. Lot sizes are constrained by amount parameters.&#x20;

* Anyone can purchase a lot (within size constraints)
* All purchases are filled immediately at the current auction price with no slippage or fees
* Tokens are immediately distributed to the purchaser
* There is no bidding process, users just purchase at current auction price
* If the auction reaches the minimum floor, it will maintain that price until the next purchase

The auction will continue until all tokens are purchased (auction completes). We retain the right to pause the auction at any time and for any reason.

## participation and timeline

The auction is open to anyone and requires no pre-registration or qualification. We have are providing an interface for interacting with the contract, but anyone is free to bypass the interface and interact with the contract directly. The same lots are offered at the same price to everyone at the same time.&#x20;

_Thank you Avalanche._

The auction will beginning marks the official start (t=0) of the wesmol launch event. Presale distributions will occur within an hour of the auction start.

## parameters

The below parameters have been built into the contract that allow the auction to change over time. The initial launch parameters will be set to the below values:

* Minimum purchase: 40 AVAX initially, eventually reduced to 20 AVAX
* Maximum purchase: 200 AVAX
* Starting price: 4,000 SMOL per AVAX  |  0.00025 AVAX per SMOL (equal to presale price)
* Price floor: 25,000 SMOL per AVAX  |  0.00004 AVAX per SMOL
* Price multiplier: 1.1x (10% increase)
* Decay rate: Adjusted as needed

_All parameters may be adjusted to ensure optimal participation and fair distribution_
