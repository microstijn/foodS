```mermaid
---
title: Schema 1 - Risico-inventarisatie en Wachttijd
---
graph TD
    subgraph Start
        A[Ik wil irrigeren]
    end
    subgraph X ["<div style="width:35em; height:2em; display:flex; justify-content: flex-start; align-items:flex-end;">Stap 1: Urgentie bepalen</div>"]
        D1{"Wanneer wordt er geoogst?"}
    end

    subgraph Y ["<div style="width:28em; height:2em; display:flex; justify-content: flex-start; align-items:flex-end;">Stap 2: Risico inventariseren</div>"]
        D2{"Risicosituatie aanwezig?<br/>(Lozing, overstort, mestafspoeling, grote groepen vogels)"}
    end

    subgraph "Actie & Conclusie"
        E["✅ Je kan irrigeren<br/>*(Let op persoonlijke veiligheid: nevel/inslikken)*"]
        F[✅ Je kan irrigeren]
        G[❗ Wachttijd bepalen<br/>via Risico Matrix]
        G_note["**Risico Matrix**<br/>Stroomsnelheid vs Waterstand<br/>Wachttijd: 1 tot 5 dagen"]
    end

    A --> D1
    D1 -- "Meer dan 2 weken" --> E
    D1 -- "Binnen 2 weken" --> D2
    
    D2 -- "Nee" --> F
    D2 -- "Ja" --> G
    
    G --- G_note
```

```mermaid
---
title: Schema 2 - Actieplan bij Acute Waterbehoefte
---
graph TD
    subgraph Start
        S1[Ik moet NU irrigeren]
    end

    subgraph Beslissingsroute
        D1{"Is het water écht nu nodig?"}
        D2{"Komt water op<br/>eetbaar deel van het gewas?"}
        D3{"Veiligere techniek mogelijk?<br/>(bv. druppelirrigatie)"}
        D4{"Zijn er >3 eerdere metingen<br/>van deze situatie?"}
        D5{"Waren die metingen<br/>binnen de norm?"}
    end

    subgraph "Actie & Conclusie"
        A1[❌ Wacht of gebruik ander water]
        A2[✅ Je kan irrigeren]
        A3[❌ Irrigeer NIET<br/><i>Laat nu meten voor de toekomst</i>]
    end
    
    S1 --> D1
    D1 -- "Nee" --> A1
    D1 -- "Ja" --> D2
    
    D2 -- "Nee" --> A2
    D2 -- "Ja" --> D3
    
    D3 -- "Ja, wordt toegepast" --> A2
    D3 -- "Nee" --> D4
    
    D4 -- "Nee" --> A3
    D4 -- "Ja" --> D5
    
    D5 -- "Ja" --> A2
    D5 -- "Nee" --> A1

    %% Styling
```

```mermaid
---
title: Risico Matrix voor Wachttijd Irrigatie
---
graph TD
    %% Row 1: Column Headers
    Blank(" ") --- Header_X1("Waterstand: Laag<br/>(weinig verdunning)") --- Header_X2("Waterstand: Hoog<br/>(veel verdunning)");

    %% Row 2: Low Flow Speed
    Header_Y1("Stroomsnelheid: Laag<br/>🐢 weinig afvoer") --- Cell_11("5<br/>dagen") --- Cell_12("3-4<br/>dagen");

    %% Row 3: High Flow Speed
    Header_Y2("Stroomsnelheid: Hoog<br/>🐇 veel afvoer") --- Cell_21("2<br/>dagen") --- Cell_22("1<br/>dag");

    %% Styling
    style Blank fill:none, stroke:none;
    
    classDef header fill:#e9ecef,stroke:#333,color:#000,font-weight:bold;
    classDef rowHeader fill:#f8f9fa,stroke:#333,color:#000,font-weight:bold;
    
    classDef highRisk fill:#f8d7da,stroke:#721c24,color:#721c24,font-weight:bold,font-size:16px;
    classDef medRisk fill:#fff3cd,stroke:#856404,color:#856404,font-weight:bold,font-size:16px;
    classDef lowRisk fill:#d4edda,stroke:#155724,color:#155724,font-weight:bold,font-size:16px;

    class Header_X1,Header_X2 header;
    class Header_Y1,Header_Y2 rowHeader;
    class Cell_11 highRisk;
    class Cell_12,Cell_21 medRisk;
    class Cell_22 lowRisk;
```
