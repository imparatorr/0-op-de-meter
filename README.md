# 0-op-de-meter

Home Assistant blueprints voor 3-fase P1-meters (Nederlandse/Belgische slimme meters).

Elke DSMR/P1-slimme meter saldeert per moment over de 3 fasen: de som van
L1 + L2 + L3 bepaalt of je afneemt of teruglevert, ook al zit je verbruik
en opwek scheef verdeeld over de fasen. Deze blueprints maken dat inzichtelijk
in Home Assistant, zonder dat je zelf template-YAML hoeft te schrijven — je
kiest gewoon je 3 fase-sensoren via een keuzemenu in de Home Assistant-interface.

## Blueprints

### 📊 P1 Netto Vermogen
Berekent de som van je 3 fasen (L1 + L2 + L3): het exacte getal dat je
slimme meter gebruikt om te bepalen of je afneemt (positief) of
teruglevert (negatief) aan het net. Dit is het "0 op de meter"-principe.

**Bestand:** [`template/p1_netto_vermogen.yaml`](template/p1_netto_vermogen.yaml)

**Direct importeren in Home Assistant:**
```
https://raw.githubusercontent.com/imparatorr/0-op-de-meter/main/template/p1_netto_vermogen.yaml
```

### ⚖️ P1 Fase Onbalans *(binnenkort beschikbaar)*
Berekent het verschil tussen de zwaarst- en lichtst-belaste fase, zodat je
kunt zien hoe scheef je verbruik fysiek verdeeld is over L1/L2/L3 —
los van wat de meter uiteindelijk afrekent.

## Installatie

1. Ga in Home Assistant naar **Instellingen → Automatiseringen & scenario's → Blueprints**
2. Klik rechtsonder op **Blueprint importeren**
3. Plak de importlink van de gewenste blueprint (zie hierboven)
4. Klik **Bekijken** → **Importeren**
5. Klik op de geïmporteerde blueprint → **Sjabloon aanmaken**
6. Kies via de keuzemenu's je eigen L1/L2/L3 vermogen-sensoren
   (bijvoorbeeld van de HomeWizard P1, DSMR Reader, P1 Monitor, of ADA P1 Meter integratie)
7. Klaar — de nieuwe sensor verschijnt meteen in Home Assistant

## Benodigdheden

- Home Assistant 2024.6.0 of nieuwer (vereist voor sjabloon-blueprints)
- Een werkende P1/DSMR-integratie die per fase een vermogen-sensor levert
  in Watt (bijvoorbeeld `sensor.p1_meter_..._active_power_l1`)

## Bijdragen

Suggesties, verbeteringen of eigen blueprints zijn van harte welkom.
Open gerust een melding of stuur een wijzigingsvoorstel in.

## Licentie

Vrij te gebruiken en aan te passen.
