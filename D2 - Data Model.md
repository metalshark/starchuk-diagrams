## Basics
```d2
Account__c: {
  shape: sql_table
  Name: String(80)
  Company: String(80)
}

Contact__c: {
  shape: sql_table
  First Name: String(80)
  Last Name: String(80)
  Account: Lookup to Account__c
}

Contact__c.Account -> Account__c
```
## Adding a Title
```d2
title: My Custom Data Model {
  near: top-center
  shape: text
  style: {
    font-size: 36
  }
}

Account__c: {
  shape: sql_table
  Name: String(80)
  Company: String(80)
}

Contact__c: {
  shape: sql_table
  First Name: String(80)
  Last Name: String(80)
  Account: Lookup to Account__c
}

Contact__c.Account -> Account__c
```
## Combined
```d2
title: Our Custom Data Model {
  near: top-center
  shape: text
  style: {
    font-size: 36
  }
}

Account__c: {
  shape: sql_table
  Name: String(80)
  Company: String(80)
}

Contact__c: {
  shape: sql_table
  First Name: String(80)
  Last Name: String(80)
  Account: Lookup to Account__c
}

Contact__c.Account -> Account__c

Account__c: {
  shape: sql_table
  Name: String(80)
  Loyalty: String(80)
}

AccountContract__c: {
  shape: sql_table
  Start: DateTime
  End: DateTime
  Account: Master Detail to Account__c
  Contract: Master Detail to Contract__c
}

Contract__c: {
  shape: sql_table
  Name: String(80)
}

AccountContract__c.Account -> Account__c
AccountContract__c.Contract -> Contract__c
```
