## Getting Transactions on the chain

#### Request
\* = Requiered
| Property  | Value                               |
|-----------|-------------------------------------|
| *Endpoint       | GET `https://api.bitclout.com/get-exchange-rate`       |

<h4><a href="#Payload">Response</a></h4>
<pre>
{
    "SatoshisPerBitCloutExchangeRate": Integer,
    "NanosSold": Integer,
    "USDCentsPerBitcoinExchangeRate": Integer
}
</pre>
---

## Types

## Payload
| Type  | Description                               |
|-----------|-------------------------------------|
| "SatoshisPerBitCloutExchangeRate"       | The exchange rate of Satoshis per 1 BitClout       |
| "NanosSold"    | Total Bitclout sold in nanos            |
| "USDCentsPerBitcoinExchangeRate"       | The exchage rate of USD Cents per 1 Bitcoin  |