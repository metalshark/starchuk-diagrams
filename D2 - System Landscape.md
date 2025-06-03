
## Basic
```d2
Salesforce: {
  Sales Cloud
  Revenue Cloud
  Service Cloud
}
```
## Nested
```d2
Salesforce: {
  Sales Cloud: {
    Leads
	Opportunities
	Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }

  Service Cloud: {
    Entitlements
    Cases
    Service Contracts
  }
}
```
## Stacked
```d2
Salesforce: {
  grid-rows: 3
  Sales Cloud: {
    Leads
	Opportunities
	Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }

  Service Cloud: {
    Entitlements
    Cases
    Service Contracts
  }
}
```
## Linked
```d2
Salesforce: {
  Sales Cloud: {
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }

  Service Cloud: {
    Entitlements
    Cases
    Service Contracts
  }

  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Entitlements
}
```
## Laid Out
```d2
Salesforce: {
  grid-rows: 3
  Sales Cloud: {
    direction: right
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }

  Service Cloud: {
    Entitlements
    Cases
    Service Contracts
  }

  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Entitlements
}
```
## Same Size
```d2
Salesforce: {
  grid-rows: 3

  Sales Cloud: {
    direction: right
    Leads: {
      width: 200
    }
    Opportunities: {
      width: 200
    }
    Quotes: {
      width: 200
    }
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog: {
      width: 200
    }
    Pricing Procedures: {
      width: 200
    }
    Fulfilment Orders: {
      width: 200
    }
  }

  Service Cloud: {
    Entitlements: {
      width: 200
    }
    Cases: {
      width: 200
    }
    Service Contracts: {
      width: 200
    }
  }
  
  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Entitlements
}
```
## Variables
```d2
vars: {
  box-width: 200
}

Salesforce: {
  grid-rows: 3

  Sales Cloud: {
    direction: right
    Leads: {
      width: ${box-width}
    }
    Opportunities: {
      width: ${box-width}
    }
    Quotes: {
      width: ${box-width}
    }
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog: {
      width: ${box-width}
    }
    Pricing Procedures: {
      width: ${box-width}
    }
    Fulfilment Orders: {
      width: ${box-width}
    }
  }

  Service Cloud: {
    Entitlements: {
      width: ${box-width}
    }
    Cases: {
      width: ${box-width}
    }
    Service Contracts: {
      width: ${box-width}
    }
  }
  
  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Entitlements
}
```
## Minimal
```d2
Salesforce: {
  grid-rows: 3
  *.direction: right
  *.grid-rows: 1
  *.*.width: 200

  Sales Cloud: {
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }
  
  Service Cloud: {
    Service Contracts -> Entitlements
    Cases
  }
  
  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Service Contracts
}
```

## ERP
```d2
Salesforce: {
  grid-rows: 3
  *.direction: right
  *.grid-rows: 1
  *.*.width: 200

  Sales Cloud: {
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }
  
  Service Cloud: {
    Service Contracts -> Entitlements
    Cases
  }
  
  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Service Contracts
}

Salesforce.Revenue Cloud.Fulfilment Orders -> ERP.Orders
```

## Marketing
```d2
Marketing.Leads -> Salesforce.Sales Cloud.Leads

Salesforce: {
  grid-rows: 3
  *.direction: right
  *.grid-rows: 1
  *.*.width: 200

  Sales Cloud: {
    Leads -> Opportunities -> Quotes
  }

  Revenue Cloud: {
    Product Catalog
    Pricing Procedures
    Fulfilment Orders
  }
  
  Service Cloud: {
    Service Contracts -> Entitlements
    Cases
  }
  
  Sales Cloud.Quotes -> Revenue Cloud.Fulfilment Orders
  Revenue Cloud.Product Catalog -> Service Cloud.Service Contracts
}

Salesforce.Revenue Cloud.Fulfilment Orders -> ERP.Orders
```
