# SIVOM de la Vallée de l'Yerres et des Sénarts

Support for schedules provided by [SIVOM de la Vallée de l'Yerres et des Sénarts](https://www.sivom.com), serving 15 communes in the Val-de-Marne and Essonne departments (France).

## Supported communes

Boussy-Saint-Antoine, Brie-Comte-Robert, Brunoy, Combs-la-Ville, Crosne, Épinay-sous-Sénart, Mandres-les-Roses, Marolles-en-Brie, Moissy-Cramayel, Périgny-sur-Yerres, Quincy-sous-Sénart, Santeny, Varennes-Jarcy, Villecresnes, Yerres.

## Configuration via configuration.yaml

```yaml
waste_collection_schedule:
  sources:
    - name: sivom_com
      args:
        commune: COMMUNE
        street: STREET
```

### Configuration Variables

**commune** *(string) (required)*: Name of the commune in uppercase (e.g. `VILLECRESNES`, `BRUNOY`, `YERRES`).

**street** *(string) (required)*: Name of the street as shown on the SIVOM website.

## How to find your street name

1. Go to `https://www.sivom.com/mesjoursdecollectes/?v=YOUR_COMMUNE` (replace `YOUR_COMMUNE` with your commune name in uppercase).
2. Find your street in the list.
3. Copy the exact street name as displayed (e.g. `ACACIAS Allée des`).

## Examples

```yaml
waste_collection_schedule:
  sources:
    - name: sivom_com
      args:
        commune: VILLECRESNES
        street: "ACACIAS Allée des"
```

```yaml
waste_collection_schedule:
  sources:
    - name: sivom_com
      args:
        commune: BRUNOY
        street: "ABBAYE rue de l"
```

## Waste types

- **Bac vert (Résiduels)**: Household waste (green bin)
- **Bac jaune (Emballages)**: Recyclables — packaging, paper, cardboard (yellow bin)
- **Bac marron (Végétaux)**: Green waste — lawn, branches, leaves (brown bin, collected ~mid-March to mid-December)
