# budgetwise-ai-bank-core
An open-source, Plaid Core Exchange compatible AI financial categorization engine for retail banking integration.
# BudgetWise AI — Institutional Bank FDX Connector (Core Exchange Compatible)

An open-source, high-efficiency AI analytical processing engine designed to parse transaction logs, generate budget categorization metrics, and interpret voice spending queries natively inside regional bank infrastructures. 

This container is licensed under the terms of the permissive **MIT License**, meaning it is **100% free** for institutional engineering teams to clone, modify, host, and run inside private cloud clusters for zero ongoing software platform fees.

## Core Integration Architecture

BudgetWise AI is designed to match the data mapping requirements of the **Financial Data Exchange (FDX) API standard**. If your institution runs on **Plaid Core Exchange**, **Fiserv AppMarket**, or **Jack Henry core platforms**, this system can be treated as a plug-and-play local data consumer proxy layer.

### Inbound Endpoint Configuration Specification

To bypass external consumer connection login screens and stream customer ledger details directly into the internal BudgetWise AI processing modules, your server architecture must direct raw data streams to follow this standardized layout parameter:

#### POST `/api/v1/fdx/transactions`

Processes account record data arrays directly into the automated AI categorization layer.

* **Authorization Header:** `Bearer <Your_Internal_System_Token>`
* **Content-Type Header:** `application/json`

##### Required Request Body Data Payload (FDX Format Mapping):
```json
{
  "accountDescriptor": {
    "accountId": "acc_99281742_biz",
    "accountType": "DEPOSIT",
    "lineOfBusiness": "COMMERCIAL"
  },
  "transactionList": [
    {
      "transactionId": "tx_883011942",
      "amount": -142.50,
      "postedDateTime": "2026-10-03T09:30:00Z",
      "description": "AWS CLOUD INFRASTRUCTURE BILLING",
      "status": "POSTED",
      "category": "Technology/Software"
    },
    {
      "transactionId": "tx_883011943",
      "amount": -18.75,
      "postedDateTime": "2026-10-03T11:15:00Z",
      "description": "REPLIT DEPLOYMENT SERVICES SUBSCRIPTION",
      "status": "POSTED",
      "category": "Business Services"
    }
  ]
}
```

##### Successful Data Processing Response Matrix (200 OK):
```json
{
  "status": "SUCCESS",
  "processedTimestamp": "2026-10-03T11:45:02Z",
  "recordsIngested": 2,
  "aiMetrics": {
    "budgetHealthScore": 88.4,
    "voiceCommandIndex": "READY",
    "anomalousSpendingDetected": false
  }
}
```

## B2B Architecture Custom Integration & Enterprise Implementation Services

While the absolute core software system code can be compiled and deployed on your infrastructure completely for free, our engineering team is available on a contract consultant basis to assist with manual technical hurdles:
* **Custom UI/UX Theme Styling:** Shaping the frontend engine to seamlessly match your mobile application's strict design language parameters.
* **On-Premise Core Database Integration Support:** Direct legacy mapping engineering for custom financial record ledgers that fall outside standard FDX API scopes.

For custom contract development pricing structures, please open a formal service issue or contact our integration desk directly.
