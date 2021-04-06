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
- Using a proxy will be the most effective solution to API restrictions. I recommend using a [Cloudflare Workers Bypass](https://github.com/jychp/cloudflare-bypass) to accomplish such. It will allow you to bypass Cloudflare, and not worry about cors. Another applicable solution will be to use a browser proxy. Such a proxy would rely on a headless browser to load BitClout.com, and then execute js fetch on the page with your request.

## Notes
- All of the documentation in this repository is for the BitClout.com Node API, however, such documentation applies to all other nodes using their API. Upon nodes becoming open source, this documentation will also apply to all private and public nodes which run an instance of the public API.
- These docs are created by engineers in the community, for engineers in the community. If you build something cool with their help, please add them to the projects tab!
- Not all nodes run the full API. For example, the Blue node does not run the Explorer API endpoints. We recommend using the main BitClout.com API for full coverage.
- These docs are put into a folder by task. For example, the Explorer folder includes documentation for both the `get-transactions` and `block` endpoint, as both are used to get chain data on the explorer.

## Contributors
- Listed below are all contributors who have assisted in the creation of these docs:
  - Hunter Paulson <HPaulson@SeismicCore.com>
  - Joe Rawlings <http://www.joerawlings.com>
