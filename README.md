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
code":200,"source":"A","time":0.007825851440429688,"limit":10000,"offset":null,"rows":1,"pre_rows":1,"total_rows":1,"state":600767,"cache":{"live":true,"duration":60,"since":"2019-10-23 21:33:00","until":"2019-10-23 21:34:00","time":null},"api":{"version":"2.0.38","last_major_update":"2019-07-19 18:07:19","next_major_update":null,"documentation":"https:\/\/github.com\/Blockchair\/Blockchair.Support\/blob\/master\/API.md","notice":"Beginning July 19th, 2019 all applications using Blockchair API on a constant basis should apply for an API key (mailto:info@blockchair.com)"}}}
Here are some considerations:

If you're building a web app, your users shouldn't make direct API requests from there. While we don't have any limitations in our CORS policy (API currently responds with a Access-Control-Allow-Origin: * header), that policy may be changed in the future without any warnings
Please don't use some random keys in your requests (e.g. ?random_key=random_value) as this can result in a 400 error (though we don't force this rule at the moment for most of our endpoints)
If you're using the API with an API key, you should keep it in secret. In order to build an app for public use using our API, you should build a proxy, so the requrst flow will look like the following: user → https://your-proxy/{:request_string} → https://api.blockchair.com/{:request_string}?key={:api_key} — that way you won't disclose the key to your users
The only exception to the "requests should be made using GET" rule is the Broadcasting transactions endpoint accepting POST requests
Basic API response
API returns JSON-encoded data. Typically, the response is an array consisting of two subarrays:

data — contains the data you requested

context — contains some metadata, e.g. a status code, query execution time, used options, etc. Here are some of it (note that not all endpoints return all of the keys listed here):

context.code — server response code (also included in HTTP headers), can return:
200 if the request succeeded
400 if there is a user error in the request
404 for some endpoints in case there's no results (this behavior is deprecated), also if you're requesting non-existing endpoint
402, 429, 435, 436, or 437 if any limit on the number or complexity of requests is exceeded (see the list of limits, and please contact us if you'd like to increase them) — your IP address will be unblocked automatically after some time
430, 434, or 503 if your IP address is temporarily blocked
500 or 503 in case of a server error (it makes sense to wait and repeat the same request or open a ticket at https://github.com/Blockchair/Blockchair.Support/issues/new or write to info@blockchair.com)
context.error — error description in the case there's an error
context.state — number of the latest known block (e.g., for all requests to endpoints connected to the Bitcoin blockchain this will yield the latest block number for Bitcoin). For
for Bitcoin). For example, it may be useful to calculate the number of network сonfirmations, or correctly iterate trough the results using ?offset=. Not returned if the request has failed.
context.state_layer_2 — the latest block number for which our engine has processed second layer (e.g. ERC-20) transactions. If it's less than the block id in your current environment (e.g. block id of a transaction you requested), it makes sense to repeat the request after some time to retrieve second layer data. With our current architecture it always equals to context.state, but that may change in future.
context.results — contains the number of found results (dashboard and raw endpoints)
context.limit — applied limit to the number of results (the default one or user set in the ?limit= query section)
context.offset — applied offset (the default one or user set in the ?offset= query section)
context.rows — contains the number of shown rows returned from the database (infinitable endpoints)
context.total_rows — total number of rows meeting the request (infinitable endpoints)
context.api — array of data on the status of the API:
context.api.version — version of API
context.api.last_major_update — timestamp of the last update, that somehow has broken backward compatibility for "stable" endpoints
context.api.next_major_update — timestamp of the next scheduled update, that can break compatibility, or null, if there are no updates scheduled
context.api.documentation — an URL to the latest version of documentation
context.api.notice — just a text notice which, for example, may describe upcoming changes (this is an optional field)
context.cache — array of info on whether the response comes from the cache or not
context.cache.live — false if the response comes from the cache, true otherwise
context.cache.until — cache expiry timestamp
context.request_cost — API request cost (1 for ordinary queries, more than 1 for complex requests, see the next section for details)
There are also some things which are the same across all endpoints:

All timestamps are in the UTC timezone, and have the following format: YYYY-MM-DD hh:ii:ss . If you require an ISO 8601 timestamp with the timezone, just replace the space with a T, and append Z to the timestamp (e.g. 2009-01-03 18:15:05 will then become 2009-01-03T18:15:05Z)
There are some endpoints allowing you to request data in formats other than JSON (e.g. TSV or CSV). In that case, the API returns plain output data in the desired format without metadata
Most of the responses are cached for some amount of time. Bypassing cache is allowed in some of our Premium API plans (see the next documentation section)
API rate limits, API keys, and Premium API
While we do allow to perform some amount of requests free of charge, generally our API is not free to use.

Here's our policy:

If you use our API occasionally for personal use or testing up to 1440 requests a day (1 request a minute in average) — a key is not required
Non-commercial and academic projects which require up to 1440 requests a day — a key is not required
Non-commercial and academic projects requiring more than 1440 requests a day should apply for a Premium API key, and are subject to a discount up to 50%
Non-commercial and academic projects requiring more than 1440 requests a day which are also Blockchair partners are subject to a discount up to 100%
Commercial projects should apply for a key to Premium API not depending on the required number of requests
Commercial projects which are also Blockchair partners (e.g. linking to Blockchair from the app's interface) are subject to a discount up to 10%
Up to 1440 requests a day	More than 1440 requests a day
Personal or testing	Key is not needed	Key is required
Non-commercial or academic	Key is not needed	Key is required, up to 100% discount
Commercial	Key is required	Key is required, up to 10% discount
Our Premium API plans are available here: https://blockchair.com/api/plans, please contact us if you have any questions or would like to have a custom plan.

The daily request counter is reset at 00:00 UTC every day.

There's an additional hard limit of 30 requests per minute on the free plan.

If you exceed the limit, an error 402 or 429 will be returned. On some of our Premium API plans it's possible to "borrow" requests from the next day if you hit the limit (if your daily limit is n and you hit it, n more requests will be added to the limit for 1 day, you will be notified, and your subscription period will shrink by 1 day) — this behavior is turned off by default.

There's an additional soft limit of 5 requests per second on both free and paid plans. This limit is applied only if we experience a very high load on our servers, and it's turned on and off manually by our admins. In case you hit this limit, an error 435 will be returned.

If you have exceeded the limit multiple times without using a key, an error 430, 434, or 503 may be returned meaning that you've been blocked. It's also possible to get automatically blocked without exceeding the limit in case we're seeing botnet usage in order to bypass the limit. If you've been blocked and you believe you haven't abused our API above the limit, please contact us. If you're using a valid API key it's not possible to get blocked; if you've been previously blocked and starting to use a key, you'll get automatically unblocked.

Please note that some of API requests may "cost" more than 1 request. Here's an example:

https://api.blockchair.com/bitcoin/dashboards/block/0 — requesting information about one block via one request "costs" 1 request
https://api.blockchair.com/bitcoin/dashboards/blocks/0,1,2,3,4,5,6,7,8,9 — requesting information about ten blocks via one request "costs" 1.9 requests
Every API endpoint documentation has the "Request cost formula" section describing how the "cost" is calculated. For most API requests it's always 1. It's more than 1 in cases when you're requiring additional data (e.g. when you're requesting data on an Ethereum address, and you're also requesting its ERC-20 token balances).

Every API response yields context.request_cost with the request cost number ("request points").

As a kindly reminder, there are tasks such as extracting lots of blockchain data (e.g. all transactions over a 2 month period) which require lots of requests done — it may be better to use our Database dumps feature instead of the API (see https://blockchair.com/dumps for documentation)

What are the steps to acquire an API key?

Our Premium API dashboard is available here: https://api.blockchair.com/premium

First, you need to choose a suitable plan: https://blockchair.com/api/plans

At the moment, this automated system accepts PayPal payments only (which also allows you to pay with your card). If you'd like to pay via wire transfer or crypto, please contact us at info@blockchair.com

Once you've paid, you will receive a one-time password which can be used to generate and activate your API key. Enter it on this page into the "I want to activate an API key I've just purchased..." form, then fill in a small form about yourself, and you'll get the key.

After you have received a key, you can track your stats and extend your subscription. Enter your API key on this page into the "I already have an API key and would like to see some stats or extend my subscription..." form. If you'd like to extend your subscription, you'd need to buy a one-time extension password and enter it on your key management page.

If you have any questions about how to buy and use your key, you can always contact us.

In order to use an API key, you need to append ?key={:api_key} or &key={:api_key} to the end of request URLs. You should use ? if there are no other parameters in the URL, and & otherwise. Here are three examples of correct URLs with a key:

https://api.blockchair.com/bitcoin/dashboards/block/0?key=myfirstpasswordwas4321andifeltsmartaboutit

https://api.blockchair.com/bitcoin/dashboards/block/0?limit=0&key=myfirstpasswordwas4321andifeltsmartaboutit

https://api.blockchair.com/bitcoin/dashboards/block/0?key=myfirstpasswordwas4321andifeltsmartaboutit&limit=0

There's an extra API endpoint for those who have an API key allowing to track the number of request made.

API versioning and changelog
