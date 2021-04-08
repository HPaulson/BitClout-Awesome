## Get the current block

#### Request
\* = Requiered
| Property  | Value                               |
|-----------|-------------------------------------|
| *Endpoint       | GET `https://api.bitclout.com/api/v1/`       |
| *Headers    | `content-type: application/json`            |

#### Response 
<pre>
{
  "Error": String,
    <a href="#header">"Header"</a>: {
      "BlockHashHex": String,
      "Version": Integer,
      "PrevBlockHashHex": String,
      "TransactionMerkleRootHex": String,
      "TstampSecs": Integer,
      "Height": Integer,
      "Nonce": Integer
  },
  "<a href="transaction">Transactions</a>": [
    {
      "TransactionIDBase58Check": String,
      "RawTransactionHex": String,
      <a href="#input">"Inputs"</a>: [
        {
          "TransactionIDBase58Check": String,
          "Index": Integer
        }
      ]
     <a href="#output">"Outputs"</a>: [
        {
          "PublicKeyBase58Check": String,
          "AmountNanos": Integer
     ]
     "SignatureHex": String,
     "TransactionType": <a href="#txntype">TransactionType</a>
     "BlockHashHex": String,
     <a href="#output">"TransactionMetadata"</a>: {
        "BlockHashHex": String,
        "TxnIndexInBlock": String,
        "TxnType": <a href="#txntype">TransactionType</a>,
        "TransactorPublicKeyBase58Check": String,
        "AffectedPublicKeys": [
          {
            "PublicKeyBase58Check": String,
            "Metadata": <a href="#affectedpublickey-metadata">PublicKeyType</a>,
          }
        ],
        <a href="#basictransfertxindexmetadata">"BasicTransferTxindexMetadata"</a>: {
          "TotalInputNanos": Integer,
          "TotalOutputNanos" Integer,
          "FeeNanos": Integer,
          "UtxoOpsDump": String
        },
        <a href="#bitcoinexchangetxindexmetadata">"BitcoinExchangeTxindexMetadata"</a>: {
          "BitcoinSpendAddress": String,
          "SatoshisBurned": Integer,
          "NanosCreated": Integer,
          "TotalNanosPurchasedBefore": Long,
          "TotalNanosPurchasedAfter": Long,
          "BitcoinTxnHash": String
        },
        <a href="#creatorcointxindexmetadata">"CreatorCoinTxindexMetadata"</a>: {
          "OperationType": "buy" | "sell",
          "BitCloutToSellNanos": Integer,
          "CreatorCoinToSellNanos": Integer,
          "BitCloutToAddNanos": Integer
         },
        <a href="#updateprofiletxindexmetadata">"UpdateProfileTxindexMetadata"</a>: {
          "ProfilePublicKeyBase58Check": String,
          "NewUsername": String,
          "NewDescription": String,
          "NewProfilePic": String,
          "NewCreatorBasisPoints": Integer,
          "NewStakeMultipleBasisPoints": Integer,
          "IsHidden": Boolean
        },
        <a href="#submitposttxindexmetadata">"SubmitPostTxindexMetadata"</a>: {
          "PostHashBeingModifiedHex": String,
          "ParentPostHashHex": String,
          <a href="#liketxindexmetadata">"LikeTxindexMetadata"</a>: {
            "IsUnlike": Boolean,
            "PostHashHex": String
          },
          <a href="#followtxindexmetadata">"FollowTxindexMetadata"</a>: {
            "IsUnfollow": Boolean
          },
          <a href="#privatemessagetxindexmetadata">"PrivateMessageTxindexMetadata"</a>: {
            "TimestampNanos": Long
          },
          <a href="#swapidentitytxindexmetadata">"SwapIdentityTxindexMetadata"</a>: {
            < UNKNOWN TYPES >
          }
        }
      }
    }
  ]
}
</pre>
---

## Types

## Header
| Type  | Description                               |
|-----------|-------------------------------------|
| "BlockHashHex"       | Hash of the current block in hex       |
| "Version"    | Version of the current block |
| "PrevBlockHashHex"       | Hash of the previous block in hex |
| "TransactionMerkleRootHex"       | < UNKNOWN > |
| "TstampSecs"       | UNIX timestamp of the block  |
| "Height"       | The current block's height |
| "Nonce" | < UNKNOWN > |

## TxnType
| Type  | Description                               |
|-----------|-------------------------------------|
| "BASIC_TRANSFER"       | Transfer of BitClout       |
| "UPDATE_PROFILE"    | Profile Update (Name, Bio, etc)            |
| "FOLLOW"       | Follow (Or unfollow) a user |
| "CREATOR_COIN"       | Purchase (Or sell) a creator coin |
| "SUBMIT_POST"       | Create (Or hide) post  |
| "LIKE"       | Like (Or unlike) post |
| "BLOCK_REWARD" | Reward for mining a block |
| "BITCOIN_EXCHANGE" | For Purchases of $BitClout using $BTC | 
| "PRIVATE_MESSAGE" | Private message between accounts | 

## AffectedPublicKey Metadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "BasicTransferOutput"       | Public key of the user who engaged in an action       |
| "ProfilePublicKeyBase58Check"    | ???            |
| "FollowedPublicKeyBase58Check"       | Public key of the user who received a follow (Or unfollow) |
| "CreatorPublicKey"       | Public key of the creator whose coin was purchased (Or sold) |
| "PosterPublicKeyBase58Check"       | Public key of the liked posts author  |

## Transaction
| Type  | Description                               |
|-----------|-------------------------------------|
| "TransactionIDBase58Check"       | Transaction ID in Base 58      |
| "RawTransactionHex"    | Raw Hex Transaction ID            |
| "Inputs"       | Array of Transaction Inputs |
| "Outputs"       | Arrat of Transaction Outputs |
| "SignatureHex"       | Transaction Signature in Hex  |
| "TransactionMetadata"       | Transaction Meta Data  |

## Input
| Type  | Description                               |
|-----------|-------------------------------------|
| "TransactionIDBase58Check"       | Transaction ID in Base 58      |
| "Index"       | < UNKNOWN >      |

## Output
| Type  | Description                               |
|-----------|-------------------------------------|
| "PublicKeyBase58Check"       | Author's Pulic Key in Base 58      |
| "AmountNanos"       | < UNKNOWN >      |

## TransactionMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "BlockHashHex"       | Transaction's block in hex |
| "TxnIndexInBlock"       | Transaction's index in it's block      |
| "TxnType"       | Transaction Type      |
| "AffectedPublicKeys"       | Array of users affected by the transaction      |
| "BasicTransferTxindexMetadata"       | Nano metadata
| "BitcoinExchangeTxindexMetadata"       | Bitcoin exchange metadata      |
| "CreatorCoinTxindexMetadata"       | Creator Coin transaction metadata      |
| "UpdateProfileTxindexMetadata"       | Profile Update meta data      |
| "SubmitPostTxindexMetadata"       | Created (Or hidden) post's metadata      |
| "LikeTxindexMetadata"       | Meta data of liked (Or unliked) post      |
| "FollowTxindexMetadata"       | Meta data of follow (Or Unfollow)      |
| "SwapIdentityTxindexMetadata"       | < UNKNOWN >      |

## BasicTransferTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "TotalInputNanos"       | Nano's inputed into the transaction |
| "TotalOutputNanos"       | Nano's outputted into the transaction |
| "FeeNanos"       | Nano fee paid for the transaction (Input - Output) |
| "UtxoOpsDump"       | < UNKNOWN > |

## BitcoinExchangeTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "BitcoinSpendAddress" | Public key address of incoming satoshis|
| "SatoshisBurned" | $BTC spent on $BitClout|
| "NanosCreated" | < UNKNOWN >|
| "TotalNanosPurchasedBefore" | < UNKNOWN >|
| "TotalNanosPurchasedAfter" | < UNKNOWN >|
| "BitcoinTxnHash" | Tx Hash of $BTC transaction|

## CreatorCoinTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "OperationType"       | Transaction Type, `"buy"` or `"sell"` |
| "BitCloutToSellNanos"       | BitClout paid for creator coin |
| "CreatorCoinToSellNanos"       | Creator Coin sold for BitClout |
| "BitCloutToAddNanos"       | < UNKNOWN > |

## UpdateProfileTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "ProfilePublicKeyBase58Check"       | User's public key in Base 58 |
| "NewUsername"       | User's new username |
| "NewDescription"       | User's new bio |
| "NewProfilePic"       | User's new profile image |
| "NewCreatorBasisPoints"       | < UNKNOWN > |
| "NewStakeMultipleBasisPoints"       | < UNKNOWN > |
| "IsHidden"       | < UNKNOWN > |

## SubmitPostTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "PostHashBeingModifiedHex"       | Transaction ID of the modified post |
| "ParentPostHashHex"       | Transaction ID of the parent post (When the modified post is a reply) |

## LikeTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "IsUnlike"       | Whether the transaction was an unlike (rather than a like) |
| "PostHashHex"       | Transaction ID of the liked post |

## FollowTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "IsUnfollow"       | Whether the transaction was an unfollow (rather than a follow) |

## PrivateMessageTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "TimestampNanos"       | < UNKNOWN > |

## SwapIdentityTxindexMetadata
| Type  | Description                               |
|-----------|-------------------------------------|
| "< UNKNOWN TYPES >"       | < UNKNOWN > |

