# Improve Documentation using OpenAI

## Problem

Our [OpenBB Bot documentation](https://docs.openbb.co/bot/reference/discord) main description was rather simplistic.

For instance, the description for our command `/dp alldp` was: "Last 15 Darkpool Trades".

## Proof-of-concept

So I fed the following prompt to [ChatGPT](https://chat.openai.com/):

> "Context: You are a developer writing a detailed documentation for a function that allows the user to retrieve Last 15 Darkpool Trades utilizing the command `/dp alldp ticker`. How would you write a clear description for this command."

And the output was a much better description:

> "The /dp alldp ticker command is a function that allows the user to retrieve the last 15 Darkpool Trades for a given ticker symbol. Darkpool trades are executed off-exchange, meaning they are not visible to the general public until after the trade has been completed. This command retrieves the most recent 15 trades for the given ticker symbol, providing the user with valuable information about the price and volume of trades executed off-exchange. This function can be used to gain insights into market sentiment and potentially inform trading strategies."

## Solution

Thus I created a script that iterated through all our documentation and updated the old description with a more detailed one.

This is the template that i used

> "Context: You are a developer writing a detailed documentation for a function that allows the user to retrieve {desc} utilizing the command {example} how would you explain what this command does in a single paragraph"

where {desc} and {example} corresponds to the current description and example that each of our commands have, respectively.

The result can be seen below,

<img width="1470" alt="Screenshot 2023-04-01 at 10 41 25 PM" src="https://user-images.githubusercontent.com/25267873/229334976-f6fcdb88-2fa9-4c6e-824d-e3bda287f810.png">
