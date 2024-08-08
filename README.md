# Insights Analysis

## Regions
- **The Worst**: "Восточний регион" - 67%
- **The Better**: "Северний" - 119%

## Managers
- **Most Productive**: Manager 3 - 192%
- **Least Productive**: Manager 5 - 30%

## Clients
- **Client with Most Overdelivered (by percentage)**: 1075%
- **Client with Most Overdelivered (by volume)**: Client 191 - 20.9k tons
- **Clients with No Delivery**: 30, 48, 47, 62, 16, 63, 15, 28, 64, 49, 14, 29, 67, 61, 66, 65

---

## Formulas:

### To map the Status to the Base:
```excel
=IFERROR(VLOOKUP(A2,'Статус менеджера'!$A$2:$B$48,2,TRUE),"")
```
### Calculation of the Tariff

```excel
=IFERROR(IF(G2 <= H2, 8,
IF(G2 <= I2, 8 + (G2 - H2) * (12 - 8) / (I2 - H2),
IF(G2 <= J2, 12 + (G2 - I2) * (20 - 12) / (J2 - I2),
IF(G2 <= K2, 20 + (G2 - J2) * (30 - 20) / (K2 - J2),
30)))),"")
```


### Calculation of the bonus

```excel
=IFERROR(IF(AND(M2="Продавець малим клієнтам", OR(B2="Східний регіон",
B2="Західний регіон", B2="Північний регіон", B2="Південний регіон", B
```
