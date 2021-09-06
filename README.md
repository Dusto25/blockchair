# blockchair
Bitcoin
Please read our statement on the November 15th, 2020 Bitcoin Cash split: https://twitter.com/Blockchair/status/1324424632179576832. It is expected that Bitcoin ABC's hashrate will be very low so 51% attacks are possible. We'll be running Bitcoin ABC in beta mode and we don't guarantee neither its stability, nor that we'll run it if the chain won't be used by businesses. Once the situation becomes more stable we'll update the documentation. At the moment, other parts of the documentation don't reflect Bitcoin ABC support, so please assume that for every bitcoin-cash endpoint there's a bitcoin-abc equivalent except for https://api.blockchair.com/bitcoin-cash/nodes.

There are also following testnets supported which are technically considered as separate blockchains:

Blokchain	Group	API path prefix	Support status
Bitcoin Testnet	Bitcoin-like	https://api.blockchair.com/bitcoin/testnet	Full support
Ethereum Goerli Testnet	Ethereum-like	https://api.blockchair.com/ethereum/testnet	Development mode, no guaranteed stability
We aim to support more blockchains (and their testnets) in future to cover as many users as possible. We don't disclose which blockchains we'll add next and how we choose them, but our main markers are daily number of real transactions and market capitalization. If you're representing a coin community which would like to add its blockchain to our platform, we'd be happy to talk.

As a general rule, if we add a blockchain to our platform, it means we'll support it and related functions indefinitely. However, there are some exceptions:

Since a blockchain system can be an unstable product, we may cease support in case the blockchain itself (or the node software we're using) stops to function or starts to function improperly;
If a blockchain hard-forks and that results in a new ruleset we can't support for technical or other reasons, we may either drop support for this blockchain, or don't accept the new ruleset;
If a blockchain is community-backed, we guarantee support till some specified date (this is reflected in the tables above). If its community decides not to prolong the agreement with Blockchair after that date, we may either continue to support that blockchain for free, or drop support for it;
If we see that a particular blockchain became unpopular on our platform, we may terminate its support with a 3 month notice.
For some of the blockchains we support we don't store full historical data. These blockchains are: Ripple, Stellar, EOS. That means you won't be able to query some old blocks, and the transaction list for an address may not show some old transactions. See Available block ranges API endpoint to get data on which blocks are available in these blockchains. All other blockchains have full historical data. It's our intent to have full historical data for all blockchains.

Blockchair API also supports 2 layer 2 solutions (tokens) divided into 2 groups:

Omni-like tokens (Omni Layer on top of Bitcoin)
ERC-20-like tokens (ERC-20's on top of Ethereum)
Like with blockchains, within a group, there's no or little difference between the available endpoints.

Layer 2	Group	Parent blockchain	API path prefix	Support status
Omni Layer	Omni-like	Bitcoin	https://api.blockchair.com/bitcoin/omni	Alpha support
ERC-20	ERC-20-like	Ethereum	https://api.blockchair.com/ethereum/erc-20	Beta support
We also plan to bring ERC-721 support in the future.

Ethereum Goerli Testnet also supports ERC-20's.

Wormhole support was dropped on January 1st, 2020 with a 3-month notice as it's not used by anyone anymore.

Quick endpoint reference
This is the full list of available API endpoints.

{:btc_chain} can be one of these: bitcoin, bitcoin-cash, litecoin, bitcoin-sv, dogecoin, dash, groestlcoin, zcash, ecash, or bitcoin/testnet
{:eth_chain} can be ethereum or ethereum/testnet
{:xrp_chain} can be only ripple
{:xlm_chain} can be only stellar
{:xmr_chain} can be only monero
{:ada_chain} can be only cardano
{:xin_chain} can be only mixin
{:xtz_chain} can be only tezos
{:eos_chain} can be only eos
{:xchain_token} can be tether, usd-coin, or binance-usd
Endpoint path	Docs	Base request cost	Status
General stats	—	—	—
https://api.blockchair.com/stats	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:xrp_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:xlm_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:xmr_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:ada_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:xin_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:xtz_chain}/stats	👉	1	Stable
https://api.blockchair.com/{:eos_chain}/stats	👉	1	Stable
https://api.blockchair.com/cross-chain/{:xchain_token}/stats	👉	1	Alpha
Block-related information	—	—	—
https://api.blockchair.com/{:btc_chain}/dashboards/block/{:height}₀	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/dashboards/block/{:hash}₀	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/dashboards/blocks/{:height}₀,...,{:height}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:btc_chain}/dashboards/blocks/{:hash}₀,...,{:hash}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:btc_chain}/raw/block/{:height}₀	👉	1	Unstable
https://api.blockchair.com/{:btc_chain}/raw/block/{:hash}₀	👉	1	Unstable
https://api.blockchair.com/{:btc_chain}/blocks?{:query}	👉	2	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/block/{:height}₀	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/block/{:hash}₀	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/blocks/{:height}₀,...,{:height}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/blocks/{:hash}₀,...,{:hash}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:eth_chain}/raw/block/{:height}₀	👉	1	Unstable
https://api.blockchair.com/{:eth_chain}/raw/block/{:hash}₀	👉	1	Unstable
https://api.blockchair.com/{:eth_chain}/blocks?{:query}	👉	2	Stable
https://api.blockchair.com/{:xrp_chain}/raw/ledger/{:height}₀	👉	1	Alpha
https://api.blockchair.com/{:xrp_chain}/raw/ledger/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xlm_chain}/raw/ledger/{:height}₀	👉	1	Alpha
https://api.blockchair.com/{:xmr_chain}/raw/block/{:height}₀	👉	1	Alpha
https://api.blockchair.com/{:xmr_chain}/raw/block/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:ada_chain}/raw/block/{:height}₀	👉	1	Alpha
https://api.blockchair.com/{:ada_chain}/raw/block/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/snapshot/{:height}₀	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/snapshot/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/snapshots?{:query}	👉	1	Alpha
https://api.blockchair.com/{:xtz_chain}/raw/block/{:height}₀	👉	1	Alpha
https://api.blockchair.com/{:xtz_chain}/raw/block/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xtz_chain}/raw/blocks?{:query}	👉	1	Alpha
https://api.blockchair.com/{:eos_chain}/raw/block/{:height}₀	👉	1	Alpha
Transaction-related information and actions	—	—	—
https://api.blockchair.com/{:btc_chain}/dashboards/transaction/{:hash}₀	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/dashboards/transactions/{:hash}₀,...,{:hash}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:btc_chain}/raw/transaction/{:hash}₀	👉	1	Unstable
https://api.blockchair.com/{:btc_chain}/push/transaction (POST)	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/transactions?{:query}	👉	5	Stable
https://api.blockchair.com/{:btc_chain}/mempool/transactions?{:query}	👉	2	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/transaction/{:hash}₀	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/transactions/{:hash}₀,...,{:hash}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:eth_chain}/raw/transaction/{:hash}₀	👉	1	Unstable
https://api.blockchair.com/{:eth_chain}/push/transaction (POST)	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/transactions?{:query}	👉	5	Stable
https://api.blockchair.com/{:eth_chain}/mempool/transactions?{:query}	👉	2	Stable
https://api.blockchair.com/{:xrp_chain}/raw/transaction/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xlm_chain}/raw/transaction/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xmr_chain}/raw/transaction/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:ada_chain}/raw/transaction/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/transaction/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/push/transaction (POST)	👉	1	Stable
https://api.blockchair.com/{:xtz_chain}/raw/operation/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:eos_chain}/raw/transaction/{:hash}₀	👉	1	Alpha
https://api.blockchair.com/{:eos_chain}/raw/transaction/({:block_height},{:hash})	👉	1	Alpha
Address-related information	—	—	—
https://api.blockchair.com/{:btc_chain}/dashboards/address/{:address}₀	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/dashboards/addresses/{:address}₀,...,{:address}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:btc_chain}/addresses/balances (POST, mass balance check)	👉	1 + 0.001*c	Stable
https://api.blockchair.com/{:btc_chain}/dashboards/xpub/{:extended_key}	👉	1 + 0.1*d	Beta
https://api.blockchair.com/{:btc_chain}/addresses?{:query}	👉	2	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/address/{:address}₀	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/addresses?{:query}	👉	2	Stable
https://api.blockchair.com/{:xrp_chain}/raw/account/{:address}₀	👉	1	Alpha
https://api.blockchair.com/{:xlm_chain}/raw/account/{:address}₀	👉	1	Alpha
https://api.blockchair.com/{:ada_chain}/raw/address/{:address}₀	👉	1	Alpha
https://api.blockchair.com/{:xtz_chain}/raw/account/{:address}₀	👉	1	Alpha
https://api.blockchair.com/{:eos_chain}/raw/account/{:address}₀	👉	1	Alpha
https://api.blockchair.com/multi/dashboards/addresses/{:address}₀,...,{:address}ᵩ	👉	Complex	Alpha
Special entities	—	—	—
https://api.blockchair.com/{:btc_chain}/outputs?{:query}	👉	10	Beta
https://api.blockchair.com/{:btc_chain}/mempool/outputs?{:query}	👉	2	Beta
https://api.blockchair.com/{:eth_chain}/dashboards/uncle/{:hash}₀	👉	1	Stable
https://api.blockchair.com/{:eth_chain}/dashboards/uncles/{:hash}₀,...,{:hash}ᵩ	👉	1 + 0.1*c	Stable
https://api.blockchair.com/{:eth_chain}/uncles?{:query}	👉	2	Stable
https://api.blockchair.com/{:eth_chain}/calls?{:query}	👉	10	Stable
https://api.blockchair.com/{:xmr_chain}/outputs?{:query}	👉	1	Alpha
https://api.blockchair.com/zcash/raw/validate?paymentdisclosure=zpd:...	N/A	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/round/{:hash}	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/round/({:node_hash},{:id})	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/node/{:hash}	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/graph	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/mintings?{:query}	👉	1	Alpha
https://api.blockchair.com/{:xin_chain}/raw/nodes?{:query}	👉	1	Alpha
Special second layer protocol endpoints (Omni Layer and ERC-20 tokens)	—	—	—
https://api.blockchair.com/bitcoin/omni/stats	👉	1	Alpha
https://api.blockchair.com/bitcoin/omni/dashboards/property/{:prorerty_id}	👉	1	Alpha
https://api.blockchair.com/bitcoin/omni/properties	👉	10	Alpha
https://api.blockchair.com/ethereum/erc-20/{:token_address}/stats	👉	1	Beta
https://api.blockchair.com/ethereum/erc-20/{:token_address}/dashboards/address/{:address}	👉	1	Beta
https://api.blockchair.com/ethereum/erc-20/tokens?{:query}	👉	2	Beta
https://api.blockchair.com/ethereum/erc-20/transactions?{:query}	👉	5	Beta
https://api.blockchair.com/ethereum/erc-20/{:token_address}/utils/allowance?owner={:owner_address}&spender={:spender_address}	N/A	1	Alpha
State changes	—	—	—
https://api.blockchair.com/{:btc_chain}/state/changes/block/{:block_id}	👉	5	Stable
https://api.blockchair.com/{:btc_chain}/state/changes/mempool	👉	10	Stable
https://api.blockchair.com/{:eth_chain}/state/changes/block/{:block_id}	👉	5	Stable
Misc	—	—	—
https://api.blockchair.com/range	👉	1	Stable
https://api.blockchair.com/tools/releases	👉	1	Stable
https://api.blockchair.com/tools/halvening	👉	1	Stable
https://api.blockchair.com/news (News API)	👉	1	Stable
Network nodes	—	—	—
https://api.blockchair.com/nodes	👉	1	Stable
https://api.blockchair.com/{:btc_chain}/nodes	👉	1	Stable
Special Premium API endpoints	—	—	—
https://api.blockchair.com/premium/stats?key={:api_key}	👉	0	Stable
Please note there are some endpoints which aren't listed here (most of the times they have the https://api.blockchair.com/internal prefix), but used by our web interface — these endpoints aren't meant to be used by 3rd parties.

The base request cost is used only if there are no additional parameters included in the request, and the default limits on the number of results are used. For example, if you're requesting info on ERC-20 tokens while getting data on an Ethereum address using a special parameter or increasing the number of latest transactions for this address, you may be charged additional request points. c in formulas means "number of requested entities". d means "depth" (applied to xpub lookups). Detailed cost formulas are available in the corresponding documentation sections.

Basic API request
Requests to the API should be made through the HTTPS protocol by GET requests to the domain api.blockchair.com. Here's an example request URL: https://api.blockchair.com/bitcoin/blocks?a=sum(generation)

> curl 'https://api.blockchair.com/bitcoin/blocks?a=sum(generation)'
{"data":[{"sum(generation)":1800957104497237}],"context":{"code":200
