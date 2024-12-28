# Juspay-API-Testing
Created a transaction and completed order creation and refund status for a customer
{
  "collection": {
    "info": {
      "_postman_id": "d5b58773-4cea-495e-a1e6-69ad99d2a0ab",
      "name": "Exercise 1",
      "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
      "updatedAt": "2024-12-13T07:13:58.000Z",
      "createdAt": "2024-12-13T06:10:48.000Z",
      "lastUpdatedBy": "40273946",
      "uid": "40273946-d5b58773-4cea-495e-a1e6-69ad99d2a0ab"
    },
    "item": [
      {
        "name": "BaseUrl",
        "id": "b7c14f14-c86e-4445-98c2-0c1f27a017af",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "method": "GET",
          "header": [],
          "url": {
            "raw": "{{sandbox}}",
            "host": [
              "{{sandbox}}"
            ]
          }
        },
        "response": [],
        "uid": "40273946-b7c14f14-c86e-4445-98c2-0c1f27a017af"
      },
      {
        "name": "Create customer",
        "id": "b05c7fd1-5f2b-4dea-9555-bb4efcf2e3a9",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "auth": {
            "type": "basic",
            "basic": [
              {
                "key": "username",
                "value": "91F045FE04341EF894BDE820668900",
                "type": "string"
              }
            ]
          },
          "method": "POST",
          "header": [
            {
              "key": "merchant_id",
              "value": "{{merchant_id}}",
              "type": "text"
            },
            {
              "key": "gateway_id",
              "value": "{{gateway_id}}",
              "type": "text"
            },
            {
              "key": "gateway_reference_id",
              "value": "{{gateway_reference_id}}",
              "type": "text"
            },
            {
              "key": "gateway",
              "value": "{{gateway}}",
              "type": "text"
            }
          ],
          "body": {
            "mode": "urlencoded",
            "urlencoded": [
              {
                "key": "object_reference_id",
                "value": "jandoe@gmail.com",
                "type": "text"
              },
              {
                "key": "email_adress",
                "value": "jandoe@gmail.com",
                "type": "text"
              },
              {
                "key": "mobile_number",
                "value": "1234567890",
                "type": "text"
              },
              {
                "key": "first_name",
                "value": "Jan",
                "type": "text"
              },
              {
                "key": "last_name",
                "value": "Doe",
                "type": "text"
              },
              {
                "key": "mobile_country_code",
                "value": "91",
                "type": "text"
              },
              {
                "key": "customer_id",
                "value": "cust_002",
                "type": "text"
              }
            ]
          },
          "url": {
            "raw": "{{sandbox}}/customers",
            "host": [
              "{{sandbox}}"
            ],
            "path": [
              "customers"
            ]
          }
        },
        "response": [],
        "uid": "40273946-b05c7fd1-5f2b-4dea-9555-bb4efcf2e3a9"
      },
      {
        "name": "Add card",
        "id": "19b3cc45-6c7d-4033-a7d1-9ca619e735db",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "auth": {
            "type": "basic",
            "basic": [
              {
                "key": "username",
                "value": "91F045FE04341EF894BDE820668900",
                "type": "string"
              }
            ]
          },
          "method": "POST",
          "header": [
            {
              "key": "merchant_id",
              "value": "{{merchant_id}}",
              "type": "text"
            },
            {
              "key": "gateway",
              "value": "{{gateway}}",
              "type": "text"
            },
            {
              "key": "gateway_id",
              "value": "{{gateway_id}}",
              "type": "text"
            },
            {
              "key": "gateway_reference_id",
              "value": "{{gateway_reference_id}}",
              "type": "text"
            }
          ],
          "body": {
            "mode": "urlencoded",
            "urlencoded": [
              {
                "key": "card_number",
                "value": "4242424242424242",
                "type": "text"
              },
              {
                "key": "card_exp_month",
                "value": "09",
                "type": "text"
              },
              {
                "key": "card_exp_year",
                "value": "25",
                "type": "text"
              },
              {
                "key": "card_security_code",
                "value": "123",
                "type": "text"
              },
              {
                "key": "upi_vpa",
                "value": "test123@upi",
                "type": "text"
              },
              {
                "key": "merchant_id",
                "value": "{{merchant_id}}",
                "type": "text"
              },
              {
                "key": "customer_id",
                "value": "cust_002",
                "type": "text"
              },
              {
                "key": "card_bin",
                "value": "123456",
                "type": "text"
              }
            ]
          },
          "url": {
            "raw": "{{sandbox}}/card/add",
            "host": [
              "{{sandbox}}"
            ],
            "path": [
              "card",
              "add"
            ]
          }
        },
        "response": [],
        "uid": "40273946-19b3cc45-6c7d-4033-a7d1-9ca619e735db"
      },
      {
        "name": "Get card details",
        "id": "499f8485-5dba-47d7-a022-d8c932a4f3fd",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "auth": {
            "type": "basic",
            "basic": [
              {
                "key": "username",
                "value": "91F045FE04341EF894BDE820668900",
                "type": "string"
              }
            ]
          },
          "method": "GET",
          "header": [],
          "url": {
            "raw": "{{sandbox}}/cards?customer_id=cust_002",
            "host": [
              "{{sandbox}}"
            ],
            "path": [
              "cards"
            ],
            "query": [
              {
                "key": "customer_id",
                "value": "cust_002"
              }
            ]
          }
        },
        "response": [],
        "uid": "40273946-499f8485-5dba-47d7-a022-d8c932a4f3fd"
      },
      {
        "name": "Create Order",
        "id": "53692d11-49c6-4903-8175-4896ffbe098f",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "auth": {
            "type": "basic",
            "basic": [
              {
                "key": "username",
                "value": "91F045FE04341EF894BDE820668900",
                "type": "string"
              }
            ]
          },
          "method": "POST",
          "header": [
            {
              "key": "mechant_id",
              "value": "{{merchant_id}}",
              "type": "text"
            },
            {
              "key": "gateway",
              "value": "{{gateway}}",
              "type": "text"
            },
            {
              "key": "gateway_id",
              "value": "{{gateway_id}}",
              "type": "text"
            },
            {
              "key": "gateway_reference_id",
              "value": "{{gateway_reference_id}}",
              "type": "text"
            }
          ],
          "body": {
            "mode": "urlencoded",
            "urlencoded": [
              {
                "key": "order_id",
                "value": "{{order_id}}",
                "type": "text"
              },
              {
                "key": "amount",
                "value": "350",
                "type": "text"
              },
              {
                "key": "customer_id",
                "value": "cust_002",
                "type": "text"
              },
              {
                "key": "order_item",
                "value": "Biriyani",
                "type": "text"
              }
            ]
          },
          "url": {
            "raw": "{{sandbox}}/orders",
            "host": [
              "{{sandbox}}"
            ],
            "path": [
              "orders"
            ]
          }
        },
        "response": [],
        "uid": "40273946-53692d11-49c6-4903-8175-4896ffbe098f"
      },
      {
        "name": "Order status completed through UPI",
        "id": "e5384ae7-fd35-4746-966c-4fae5d553d11",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "auth": {
            "type": "basic",
            "basic": [
              {
                "key": "username",
                "value": "91F045FE04341EF894BDE820668900",
                "type": "string"
              }
            ]
          },
          "method": "GET",
          "header": [],
          "url": {
            "raw": "{{sandbox}}/orders/{{order_id}}",
            "host": [
              "{{sandbox}}"
            ],
            "path": [
              "orders",
              "{{order_id}}"
            ]
          }
        },
        "response": [],
        "uid": "40273946-e5384ae7-fd35-4746-966c-4fae5d553d11"
      },
      {
        "name": "Create refund",
        "id": "465d51b0-43f3-49f4-b77c-36b54a70b074",
        "protocolProfileBehavior": {
          "disableBodyPruning": true
        },
        "request": {
          "auth": {
            "type": "basic",
            "basic": [
              {
                "key": "username",
                "value": "91F045FE04341EF894BDE820668900",
                "type": "string"
              }
            ]
          },
          "method": "POST",
          "header": [
            {
              "key": "merchant_id",
              "value": "{{merchant_id}}",
              "type": "text"
            },
            {
              "key": "gateway_id",
              "value": "{{gateway_id}}",
              "type": "text"
            },
            {
              "key": "gateway_reference_id",
              "value": "{{gateway_reference_id}}",
              "type": "text"
            },
            {
              "key": "gateway",
              "value": "{{gateway}}",
              "type": "text"
            },
            {
              "key": "routing_id",
              "value": "cust_002",
              "type": "text"
            }
          ],
          "body": {
            "mode": "urlencoded",
            "urlencoded": [
              {
                "key": "order_id",
                "value": "{{order_id}}",
                "type": "text"
              },
              {
                "key": "unique_request_id",
                "value": "63031047",
                "type": "text"
              },
              {
                "key": "amount",
                "value": "350.00",
                "type": "text"
              }
            ]
          },
          "url": {
            "raw": "{{sandbox}}/orders/{{order_id}}/refunds",
            "host": [
              "{{sandbox}}"
            ],
            "path": [
              "orders",
              "{{order_id}}",
              "refunds"
            ]
          }
        },
        "response": [],
        "uid": "40273946-465d51b0-43f3-49f4-b77c-36b54a70b074"
      }
    ]
  }
}
