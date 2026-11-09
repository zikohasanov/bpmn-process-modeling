# As-Is Process — Phone Pickup Order

## Purpose and boundary

This is a discovery hypothesis for a fictional restaurant: from a customer's phone call to pickup and payment. Validate task order and exception frequency by observing staff before treating it as an actual baseline.

```mermaid
flowchart LR
  subgraph Customer
    A((Order need)) --> B[Call restaurant]
    J[Ask for status] --> K[Arrive for pickup]
  end
  subgraph Front_of_house
    B --> C[Write items on paper]
    C --> D[Repeat order to confirm]
    D --> E{Item available?}
    E -- no --> F[Offer substitute or decline]
    F --> G{Customer agrees?}
    G -- no --> X((Order ends))
    G -- yes --> H[Pass order to kitchen]
    E -- yes --> H
    H --> I[Re-enter details in POS]
    I --> M{Correction needed?}
    M -- yes --> N[Call customer and correct]
    M -- no --> O[Wait for kitchen update]
    N --> O
    O --> P[Answer status call]
    P --> Q[Take payment at pickup]
  end
  subgraph Kitchen
    H --> R[Prepare order]
    R --> S[Signal ready to front of house]
    S --> P
  end
  Q --> T((Order collected))
```

## Risks to validate

- Is the order repeated back, and does the kitchen receive the same paper/POS representation?
- How are substitutions and unavailable items agreed and recorded?
- How often are correction calls and status calls made per 100 orders?
- Which system is the source of truth for order state?
- What happens when staff are too busy to answer the phone?
