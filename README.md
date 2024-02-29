# FirstAssignment
Tvarkingas duomenų failas (tidy data)
1. Nuskaitykite duomenų failą datasets :: WorldPhones (jame patiktas tam tikrų metų
įvairių regionų telefonų skaičius).
Apžvelkite failą datasets :: W orldP hones (kintamieji, jų tipai, eilutės). Kurie
tvarkingo failo formato kriterijai pažeisti?

```
phone <- WorldPhones
phone
#netvarkingi, nes eilutėse apie kelis kintamuosius informacija.
```
Sukurkite failo datasets :: W orldP hones kopiją ir sutvarkykite eilučių pavadinimus.
```
phone = as.data.frame(WorldPhones)
phone_copy = tibble :: rownames_to_column(phone, "Years")
```
Sukurkite naują kintamąjį T elephones - regiono telefonų skaičius (žr. pivot_longer)
ir sutvarkykite duomenų failą.

```
phone_copy %>% pivot_longer(c("N.Amer", "Europe", "Asia", "S.Amer", "Oceania",
                              "Africa", "Mid.Amer"), names_to = "Continent",
                            values_to = "Telephones")
```

