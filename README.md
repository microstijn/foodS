# Project FoodS: Handvaten voor Veilig Irrigatiewater

Dit project biedt praktische handvaten en beslissingsondersteunende hulpmiddelen voor agrariërs om veilig gebruik te maken van oppervlaktewater voor irrigatie, in lijn met de geest van de GlobalGAP-regelgeving.

## Omschrijving

Het doel van GlobalGAP is het waarborgen van de voedselveiligheid, onder andere door het testen van oppervlaktewater dat wordt gebruikt voor irrigatie. Dit project laat zien hoe agrariërs en consumenten beter beschermd kunnen worden aan de hand van simpele vuistregels, zonder dat dit veel extra moeite kost. De focus ligt op de risico's voor de menselijke gezondheid.

## Achtergrond

De GlobalGAP-wetgeving vereist doorgaans enkele metingen van het oppervlaktewater per jaar. Echter, de waterkwaliteit kan op de schaal van dagen of zelfs uren fluctueren, waardoor deze metingen alleen niet altijd een volledig beeld geven.

Dit project overbrugt die kloof door redelijke inschattingen van de waterkwaliteit mogelijk te maken, zelfs zonder directe meting. De hier gepresenteerde vuistregels zijn gebaseerd op een combinatie van modellen, risico-inschattingen, praktijkervaring en gezond boerenverstand. Metingen blijven echter een essentieel middel om onbekende situaties te evalueren.

## Doelgroep

Dit document is primair bedoeld als rugsteun voor agrariërs die te maken hebben met de GlobalGAP-regelgeving voor irrigatiewater.

## Inhoud van deze Repository

* **/word/WaterSafety_SHP_g.docx**: Het volledige brondocument met gedetailleerde uitleg over risico's, de logica achter de stroomschema's, factsheets over ziekteverwekkers en structurele ("no-regret") maatregelen.
* **/pdf/poster.pdf**: Informatieve poster die de kernboodschappen en stroomschema's samenvat voor gebruik in de praktijk.
* `README.md`: Dit bestand.

## Kern van de Aanpak: De Stroomschema's

De kern van dit project wordt gevormd door twee stroomschema's die helpen bij het nemen van een concrete actie.

### 1. Schema 1: Risico-inventarisatie en Wachttijd
Dit schema is voor geplande irrigatie en helpt te bepalen of er een risico is en hoe lang men eventueel moet wachten.

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

### 2. Schema 2: Actieplan bij Acute Waterbehoefte
Dit schema is voor situaties waarin wachten volgens Schema 1 eigenlijk niet mogelijk is door bijvoorbeeld extreme droogte[cite: 87]. 

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

## Technische Details: Mermaid Flowcharts

De flowcharts in deze repository zijn geschreven in [Mermaid syntax](https://mermaid-js.github.io/mermaid/#/). Dit is een op tekst gebaseerde manier om diagrammen te genereren.

* **Bekijken**: GitHub rendert `.md` bestanden met Mermaid-blokken automatisch als visuele diagrammen.
* **Bewerken**: U kunt de `.md` bestanden direct in een teksteditor aanpassen. Om de wijzigingen live te zien, kunt u de [Mermaid Live Editor](https://mermaid.live) gebruiken.


