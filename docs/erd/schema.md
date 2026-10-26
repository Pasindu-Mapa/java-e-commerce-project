```mermaid

erDiagram

&#x20;   USERS ||--o| CART : has

&#x20;   USERS ||--o{ ORDERS : places

&#x20;   CATEGORIES ||--o{ PRODUCTS : contains

&#x20;   CART ||--o{ CART\_ITEMS : contains

&#x20;   PRODUCTS ||--o{ CART\_ITEMS : added\_to

&#x20;   ORDERS ||--|{ ORDER\_ITEMS : contains

&#x20;   PRODUCTS ||--o{ ORDER\_ITEMS : referenced\_in

&#x20;   ORDERS ||--|| PAYMENTS : settled\_by



&#x20;   USERS {

&#x20;       bigint id PK

&#x20;       varchar email UK

&#x20;       varchar password\_hash

&#x20;       varchar role

&#x20;       timestamp created\_at

&#x20;   }



&#x20;   CATEGORIES {

&#x20;       bigint id PK

&#x20;       varchar name

&#x20;       varchar slug UK

&#x20;       text description

&#x20;   }



&#x20;   PRODUCTS {

&#x20;       bigint id PK

&#x20;       bigint category\_id FK

&#x20;       varchar title

&#x20;       decimal price

&#x20;       int stock\_quantity

&#x20;   }



&#x20;   CART {

&#x20;       bigint id PK

&#x20;       bigint user\_id FK

&#x20;       timestamp updated\_at

&#x20;   }



&#x20;   CART\_ITEMS {

&#x20;       bigint id PK

&#x20;       bigint cart\_id FK

&#x20;       bigint product\_id FK

&#x20;       int quantity

&#x20;   }



&#x20;   ORDERS {

&#x20;       bigint id PK

&#x20;       bigint user\_id FK

&#x20;       decimal total\_amount

&#x20;       varchar status

&#x20;       timestamp created\_at

&#x20;   }



&#x20;   ORDER\_ITEMS {

&#x20;       bigint id PK

&#x20;       bigint order\_id FK

&#x20;       bigint product\_id FK

&#x20;       int quantity

&#x20;       decimal unit\_price

&#x20;   }



&#x20;   PAYMENTS {

&#x20;       bigint id PK

&#x20;       bigint order\_id FK

&#x20;       decimal amount

&#x20;       varchar status

&#x20;       varchar transaction\_id

&#x20;       timestamp created\_at

&#x20;   }

```

