# AisiWallet-API

## General information

Following document describes AisiWallet API, which gives developers ability to build applications on AISI platform. 
This API represents RESTful service, which grants external access to AISI platform to get information about AISI accounts, 
create transactions, accounts, etc. 

In order to use API, developer must obtain API_KEY from AISI Team. You can find contact information on our website: https://aisi.io

API Endpoint: https://api.aisi.io 

After assigning API_KEY to your AISI account, you can use following methods for your application: 

## API Methods

#### 1. Get total balance

##### GET /account/balance?api_key=YOUR_API_KEY

Response: 
```
{  
"balance": "YOUR_ACCOUNT_BALANCE",  
"account_id": "YOUR_ACCOUNT_ID"
}
```



#### 2. Get balance by address 

##### GET /account/{ADDRESS}/balance?api_key=YOUR_API_KEY 

Response: 

```
{
  "balance": "YOUR_ACCOUNT_BALANCE",
  "address": "YOUR_ADDRESS"
}
```

#### 3. Generate new address 

###### POST /account/address/new?api_key=YOUR_API_KEY

Response: 
```
{
  "address": "NEW_AISI_ADDRESS"
}
```

#### 4. Create new transaction

##### POST /transaction/create/{FROM_ADDRESS}/{TO_ADDRESS}/{AMOUNT}?api_key=YOUR_API_KEY

Response: 

```
{
  "transaction_identifier" : "TRANSACTION_IDENTIFIER",
  "result": "RESULT_CODE",
  "resultMessage": "RESULT_CODE_EXPLAINED"
}
```

#### 5. Get transaction information

##### GET /transaction/details/{TRANSACTION_ID}?api_key=YOUR_API_KEY

Response: 

```
{
  "timestamp" : "TRANSACTION_TIMESTAMP",
  "sender" : "ADDRESS_OF_SENDER",
  "receiver" : "ADDRESS_OF_RECEIVER",
  "amount": "AMOUNT_TRANSFERED"
}
```



#### 6. Get transactions by address

##### GET /transaction/address/{ADDRESS}/{COUNT}?api_key=YOUR_API_KEY

Gets last {COUNT} transaction identifiers for address 

Response: 

```
[
 {
   "transaction_id" : "TRANSACTION_IDENTIFIER",
   "timestamp" : "TRANSACTION_TIMESTAMP"
 },
 ... {COUNT} objects in array 
}
```

#### 7. Get account transactions 

##### GET /transaction/account/{COUNT}?api_key=YOUR_API_KEY

Gets last {COUNT} transaction identifiers for account attached to YOUR_API_KEY 

Response: 

```
[
 {
   "transaction_id" : "TRANSACTION_IDENTIFIER",
   "timestamp" : "TRANSACTION_TIMESTAMP"
 },
 ... {COUNT} objects in array 
}
```



