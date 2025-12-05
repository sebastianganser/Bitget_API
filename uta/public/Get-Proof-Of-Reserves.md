# Get Proof Of Reserves

### Description[​](#description "Direct link to Description")

Get Proof Of Reserves

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/proof-of-reserves
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/proof-of-reserves"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1753845058586,  
  "data": {  
    "merkleRootHash": "e0dff99bbe2c2dcb",  
    "totalReserveRatio": "175%",  
    "list": [  
      {  
        "coin": "BTC",  
        "userAssets": "9530.89",  
        "platformAssets": "29679.59",  
        "reserveRatio": "311%"  
      },  
      {  
        "coin": "USDT",  
        "userAssets": "1948633388.98",  
        "platformAssets": "1985576297.93",  
        "reserveRatio": "102%"  
      },  
      {  
        "coin": "ETH",  
        "userAssets": "195465.81",  
        "platformAssets": "294561.45",  
        "reserveRatio": "151%"  
      },  
      {  
        "coin": "USDC",  
        "userAssets": "58830275.64",  
        "platformAssets": "157216065.76",  
        "reserveRatio": "267%"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| merkleRootHash | String | Merkle root hash |
| totalReserveRatio | String | Total reserve ratio   Returned in decimal form. For example, 1.99 represents 199%   Precision is two decimal places |
| list | Array | List |
| >coin | String | Currency name |
| >platformAssets | String | Platform funds Precision is two decimal places, with the unit being the corresponding currency (coin) |
| >userAssets | String | User funds Precision is two decimal places, with the unit being the corresponding currency (coin) |
| >reserveRatio | String | Reserve ratio  Returned in decimal form. For example, 1.99 represents 199% Precision is two decimal places |