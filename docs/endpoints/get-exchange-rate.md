## Getting Transactions on the chain

### Request
\* = Requiered
| Property  | Value                               |
|-----------|-------------------------------------|
| *Endpoint       | GET `https://api.bitclout.com/get-exchange-rate`       |

### Response
<pre>
{
    "SatoshisPerBitCloutExchangeRate": Integer,
    "NanosSold": Integer,
    "USDCentsPerBitcoinExchangeRate": Integer
}
</pre>

| Type  | Description                               |
|-----------|-------------------------------------|
| "SatoshisPerBitCloutExchangeRate"       | The exchange rate of Satoshis per 1 BitClout       |
| "NanosSold"    | Total Bitclout sold in nanos            |
| "USDCentsPerBitcoinExchangeRate"       | The exchage rate of USD Cents per 1 Bitcoin  |
