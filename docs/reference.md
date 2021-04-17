# BitClout API Documentation

## Reference 
- The BitClout API has multiple node API URL's available for use. They are:
  - https://api.bitclout.com
  - https://api.bitclout.blue
  - https://api.bitclout.green
  - https://api.bitclout.navy

- The base URL's above can be used for most endpoints, however for Explorer endpoints (`block` & `transaction-info`), you must add `/api/v1/`.
    
## Restrictions
- Due to heavy loads from engineers seeking to develop tools for BitClout, the development team has implemented Cloudflare Bot Protection & Strict cors policies to restrict the use of the API which doesn't originate from the client.  To hit the API, you must use an effective bypass for both CloudFlare, and cors origin. You will receive `403 Forbidden` from Cloudflare if attempting to reach the API without a working bypass.

## Solutions
- Using an API solution will be required to bypass API restrictions- you may not hit the API directly without such. To accomplish such, you may use an [Existing Public Proxy](https://www.bitcloutapi.net/), or other bypass tools such as [@Nichomacheus's Base Client](https://github.com/nichomacheus/bitclout). You should note, however, that neither of these solutions are perfect. Proxies are generally very slow, and command-line tools most likely don't fit your exact needs. For these reasons, I'd personally recommend not using such solutions in production applications. If you're building something for production use, either wait until nodes are publically available, or build a solution that specifically meets your needs -- and doesn't forget to use a speedy language and library! 

- A bypass solution such as the ones above is NOT required while building iOS applications. Apple's [Webview](https://developer.apple.com/documentation/webkit/webview) acts in a similar fashion to a browser, thus bypassing Cloudflare, while also lacking enforcement of CORS security policies- making it perfect for direct calls to the BitClout API. 

## Notes
- All of the documentation in this repository is for the BitClout.com Node API, however, upon nodes becoming open source, this documentation will also apply to all private and public nodes which run an instance of such API.

- These docs are created by engineers in the community, for engineers in the community. If you build something cool with their help, please add them to the projects tab!

- Not all nodes run the full API. For example, the Blue node does not run the Explorer API endpoints. We recommend using the main BitClout.com API for full coverage.

- These docs are put into a folder by task. For example, the Explorer folder includes documentation for both the `get-transactions` and `block` endpoint, as both are used to get chain data on the explorer.

## Discovered Endpoints
- [`GET api/v1`](https://github.com/HPaulson/BitClout/blob/master/docs/explorer/current-block.md)
- `GET get-exchange-rate`
- `POST api/v1/block`
- [`POST api/v1/transaction-info`](https://github.com/HPaulson/BitClout/blob/master/docs/explorer/transactions.md")
- `POST block-public-key`
- `POST burn-bitcoin`
- `POST buy-or-sell-creator-coin-WVAzTWpGOFFnMlBvWXZhTFA4NjNSZGNW`
- `POST buy-or-sell-creator-coin-preview-WVAzTWpGOFFnMlBvWXZhTFA4NjNSZGNW`
- `POST create-follow-txn-stateless`
- `POST create-like-stateless`
- `POST create-user-stateless`
- `POST get-app-state`
- `POST get-follows-stateless`
- `POST get-messages-stateless`
- `POST get-notifications`
- `POST get-posts-stateless`
- `POST get-profiles`
- `POST get-single-post`
- `POST get-txn`
- `POST get-users-stateless`
- `POST logout`
- `POST send-bitclout`
- `POST send-message-stateless`
- `POST submit-post`
- `POST update-user-global-metadata`
