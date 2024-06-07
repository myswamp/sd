# payment service
1. upstream services e.g. order, shipment etc. emits events via outbox.
2. ledger event system injects events in append only manner
3. ledger items and account balances are derived from ledger events
4. settlement service generates daily settlement for each merchant
5. settlement service refers to WSS to determine payment cycle and generates weekly and semi-monthly settlements for each merchant
6. settlement service calls payment executor on disbursement day to submit payments
7. update account balance when reconciliation is done