# Stati

## 0 - ch1

### Variabili

| var     | state  |
| ------  | -----  |
| chan    | 1      |
| auto    | on     |
| rate    | slow   |
| filter  | on     |
| rel     | off    |
| unità   | query? |
| shift   | off    |
| display |        |

### Passaggi di stato

| button | next state                                   |
| ------ | -------------------------------------------- |
| DCV1   | 0                                            |
| shift  | 2.1                                          |
| rel    | 0: rel -> !rel                               |
| filt   | 0: filter --> !filter                        |
| up     | 0: unità --> query?x10<br />    auto --> off |
| down   | 0: unità --> query?:10<br />    auto --> off |
| auto   | 0: auto --> !auto                            |
| rate   | 0: rate --> rate++                           |
| digits | display --> display++                        |
| temp1  | 3                                            |
| temp2  | 4                                            |
| v1/v2  | 5                                            |
| step   | 6                                            |
| scan   | 7                                            |

## 1 - shift

### Variabili

| var    | state |
| ------ | ----- |
| shift  | on    |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| v1/v2  | 9          |
| filt   | 10         |
| temp2  | 15         |
| acal   | 23         |
| shift  | !shift     |

## 2 - ch2

### Variabili

| var    | state  |
| ------ | -----  |
| chan   | 2      |
| auto   | on     |
| rate   | query? |
| filter | on     |
| rel    | off    |
| unità  | query? |
| shift  | off    |

### Passagi di stato

| button | next state                                   |
| ------ | -------------------------------------------- |
| DCV1   | 0                                            |
| shift  | 2.1                                          |
| rel    | 2: rel -> !rel                               |
| filt   | 2: filter --> !filter                        |
| up     | 2: unità --> query?x10<br />    auto --> off |
| down   | 2: unità --> query?:10<br />    auto --> off |
| auto   | 2: auto --> !auto                            |
| rate   | 2: rate --> rate++                           |
| digits | display --> display++                        |
| temp1  | 3                                            |
| temp2  | 4                                            |
| v1/v2  | 5                                            |
| step   | 6                                            |
| scan   | 7                                            |

## 3 - temp1

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1      |
| rate   | rate   |
| filter | on     |
| unità  | query? |
| shift  | off    |

### Passagi di stato

| button | next state            |
| ------ | --------------------- |
| DCV1   | 0                     |
| DCV2   | 2                     |
| shift  | 3.1                   |
| temp2  | 4                     |
| filt   | 3: filter --> !filter |
| v1/v2  | 5                     |

## 4 - temp2

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 2      |
| rate   | rate   |
| filter | on     |
| unità  | query? |
| shift  | off    |

### Passagi di stato

| button | next state            |
| ------ | --------------------- |
| DCV1   | 0                     |
| DCV2   | 2                     |
| shift  | 4.1                   |
| temp1  | 3                     |
| filt   | 4: filter --> !filter |
| v1/v2  | 5                     |

## 5 - v1/v2

### Variabili

| var     | state |
| ------- | ----- |
| chan    | 1-2   |
| rate    | rate  |
| auto    | on    |
| display | RA    |

### Passaggi di stato

| button | **next state**     |
| ------ | ------------------ |
| DCV1   | 0                  |
| DCV2   | 2                  |
| temp1  | 3                  |
| temp2  | 4                  |
| rate   | 5:rate --> rate++  |
| filt   | 5: filt --> !filt  |
| rel    | 5: rel --> !rel    |
| auto   | 5: auto --> !auto  |
| up     | query<br />range++ |
| down   | query<br />range-- |
| shift  | 5.1                |



## 6 - step

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1      |
| filter | filter |
| rate   | rate   |
| auto   | on     |
| unità  | query? |
| shift  | off    |
| step   | step   |

### Passaggi di stato

| button | next state      |
| ------ | --------------- |
| shift  | 8               |
| scan   | 7               |
| rel    | 6: rel --> !rel |

## 7 - scan

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1      |
| filter | filter |
| rel    | rel    |
| rate   | rate   |
| auto   | on     |
| unità  | query? |
| shift  | off    |
| scan   | scan   |

### Passaggi di stato

| button | next state      |
| ------ | --------------- |
| shift  | 8               |
| step   | 6               |
| rel    | 7: rel --> !rel |

## 8 - shift_bis_volt

### Variabili

| var    | state  |
| ------ | ------ |
| shift  | on     |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| scan   | 2          |

Quando viene premuto scan torna allo stato precedente, per risolvere il problema senza dover tener traccia dello stato precendente conviene riportare sia lo strumento fisico che quello virtuale allo stato 0.

## 9 - v1-v2

### Variabili

| var     | state  |
| ------  | ------ |
| chan    | 1      |
| rate    | rate   |
| filter  | filter |
| rel     | rel    |
| auto    | on     |
| display | d      |

###Passaggi di stato

| button | next state         |
| ------ | ------------------ |
| DCV1   | 0                  |
| DCV2   | 2                  |
| temp1  | 3                  |
| temp2  | 4                  |
| filt   | 9: filt --> !filt  |
| rel    | 9: rel -->!rel     |
| auto   | 9: auto --> !auto  |
| up     | query<br />range++ |
| down   | query<br />range-- |
| step   | 6                  |
| scan   | 7                  |
| digit  | 9: digit++         |



## 10 - type_analog

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **analog**+(on/off) |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| right  | 11         |
| left   | 11         |
| up     | 12         |
| down   | 12         |
| enter  | 12         |
| exit   | chan       |
| DCV1   | 0          |
| DCV2   | 2          |
| temp1  | 3          |
| temp2  | 4          |

## 11 - type_analog_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | analog+**(on/off)** |

### Passaggi di stato

| button | next state          |
| ------ | ------------------- |
| left   | 10                  |
| right  | 10                  |
| up     | 11: change analog   |
| down   | 11: change analog   |
| enter  | 12<br />save analog |
| exit   | chan                |
| DCV1   | 0                   |
| DCV2   | 2                   |
| temp1  | 3                   |
| temp2  | 4                   |

## 12 - type_digital

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | **digital**+(on/off) |

### Passaggi di stato

| button     | next state                                   |
| ---------- | -------------------------------------------- |
| left/right | 13                                           |
| up         | 10                                           |
| down       | 10                                           |
| enter      | 12: if digital==on --> 14<br />else --> chan |
| exit       | chan                                         |
| DCV1       | 0                                            |
| DCV2       | 2                                            |
| temp1      | 3                                            |
| temp2      | 4                                            |

## 13 - type_digital_bis

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | digital+**(on/off)** |

### Passaggi di stato

| button     | next state                                   |
| ---------- | -------------------------------------------- |
| left/right | 12                                           |
| up/down    | 13: digital --> !digital                     |
| enter      | 13: if digital==on --> 14<br />else --> chan |
| exit       | chan                                         |
| DCV1       | 0                                            |
| DCV2       | 2                                            |
| temp1      | 3                                            |
| temp2      | 4                                            |

## 14 - type_window

### Variabili

| var     | state                 |
| ------- | --------------------- |
| chan    | chan                  |
| display | window+**(settings)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| enter  | 26         |
| exit   | chan       |
| DCV1   | 0          |
| DCV2   | 2          |
| temp1  | 3          |
| temp2  | 4          |
| up     | window++   |
| down   | window--   |

## 15 - tcoupl_units

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | **units**+(settings) |

### Passaggi di stato

| button     | next state |
| ---------- | ---------- |
| right/left | 16         |
| up         | 21         |
| down       | 17         |
| enter      | 17         |
| exit       | chan       |
| DCV1       | 0          |
| DCV2       | 2          |
| temp1      | 3          |
| temp2      | 4          |

## 16 - tcoupl_units_bis

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | units+**(settings)** |

### Passaggi di stato

| button     | next state                |
| ---------- | ------------------------- |
| left/right | 15                        |
| enter      | save tcoupl_units<br />17 |
| exit       | chan                      |
| up/down    | change tcoupl_units       |
| DCV1       | 0                         |
| DCV2       | 2                         |
| temp1      | 3                         |
| temp2      | 4                         |

## 17 - tcoupl_sens

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **sens**+(settings) |

### Passaggi di stato

| button     | next state |
| ---------- | ---------- |
| right/left | 18         |
| up         | 16         |
| down       | 19         |
| enter      | 19         |
| exit       | chan       |
| DCV1       | 0          |

## 18 - tcoupl_sens_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | sens+**(settings)** |

### Passaggi di stato

| button     | next state               |
| ---------- | ------------------------ |
| left/right | 17                       |
| enter      | save tcoupl_sens<br />19 |
| exit       | chan                     |
| up/down    | tcoupl_sens++            |
| DCV1       | 0                        |

## 19 - tcoulp_type

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **type**+(settings) |

### Passaggi di stato

| button     | next state |
| ---------- | ---------- |
| right/left | 20         |
| up         | 17         |
| down       | 21         |
| enter      | 21         |
| exit       | chan       |
| DCV1       | 0          |

## 20 - tcoulp_type_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | type+**(settings)** |

### Passaggi di stato

| button     | next state               |
| ---------- | ------------------------ |
| left/right | 19                       |
| up/down    | change tcoupl_type       |
| enter      | save tcoupl_type<br />21 |
| exit       | chan                     |
| DCV1       | 0                        |

## 21 - tcoulp_junc

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **junc**+(settings) |

### Passaggi di stato

| button     | next state |
| ---------- | ---------- |
| right/left | 22         |
| up         | 19         |
| down       | 15         |
| enter      | chan       |
| exit       | chan       |
| DCV1       | 0          |

## 22 - tcoulp_junc_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | junc+**(settings)** |

### Passaggi di stato

| button     | next state                |
| ---------- | ------------------------- |
| left/right | 21                        |
| enter      | save coupl_junc<br />chan |
| exit       | chan                      |
| up/down    | change tcoupl_junc        |
| DCV1       | 0                         |

## 23 - Lsync

### Variabili

| var     | state                 |
| ------- | --------------------- |
| display | linesync+**(on/off)** |

### Passaggi di stato

| button  | next state           |
| ------- | -------------------- |
| enter   | save lsync<br />chan |
| exit    | chan                 |
| up/down | change lsync         |
| DCV1    | 0                    |


## 25- shift_bis_temp

### Variabili

| var   | state |
| ----- | ----- |
| shift | on    |

### Passaggi di stato

| **button** | **next state** |
| ---------- | -------------- |
| scan       | 4              |

## 26 - Type_RDGS

| var  | state |
| ---- | ----- |
| chan | chan  |

### Passaggi di stato

| button     | next state             |
| ---------- | ---------------------- |
| DCV1       | 0                      |
| DCV2       | 2                      |
| temp1      | 3                      |
| temp2      | 4                      |
| exit       | chan                   |
| enter      | save type_rdgs<br />27 |
| tastierino | on                     |

## 27 - Type_type 

### Variabili

| var  | state |
| ---- | ----- |
| chan | chan  |

### Passaggi di stato

| button  | next state               |
| ------- | ------------------------ |
| DCV1    | 0                        |
| DCV2    | 2                        |
| temp1   | 3                        |
| temp2   | 4                        |
| enter   | save type_type<br />chan |
| exit    | chan                     |
| up/down | type_type++              |

