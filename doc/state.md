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
| DCV2   | 2                                            |
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

| button | next state                                   |
| ------ | -------------------------------------------- |
| DCV1   | 0                                            |
| DCV2   | 2                                            |
| shift  | 3.1                                          |
| temp2  | 4                                            |
| filt   | 0: filter --> !filter                        |
| v1/v2  | 5                                            |

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
| filt   | 0: filter --> !filter |
| v1/v2  | 5                     |

## 5 - v1/v2

### Variabili

| var     | state |
| ------- | ----- |
| chan    | 1-2   |
| rate    | rate  |
| auto    | on    |
| display | RA    |

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

| button | next state |
| ------ | ---------- |
| shift  | 8          |

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

| button | next state |
| ------ | ---------- |
| shift  | 8          |

## 8 - shift_bis

### Variabili

| var    | state  |
| ------ | ------ |
| shift  | on     |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| scan   | ?          |

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
| up     | ?          |
| down   | 12         |
| enter  | ?          |
| exit   | ?          |

## 11 - type_analog_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | analog+**(on/off)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| left   | 10         |
| enter  | ?          |
| exit   | ?          |

## 12 - type_digital

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | **digital**+(on/off) |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| lright | 13         |
| up     | 10         |
| down   | 14         |
| enter  | ?          |
| exit   | ?          |

## 13 - type_digital_bis

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | digital+**(on/off)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| left   | 12         |
| enter  | ?          |
| exit   | ?          |

## 14 - type_window

### Variabili

| var     | state                 |
| ------- | --------------------- |
| chan    | chan                  |
| display | window+**(settings)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| enter  | ?          |
| exit   | ?          |
| up     | ?          |
| down   | ?          |

## 15 - tcoupl_units

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | **units**+(settings) |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| rght   | 16         |
| up     | ?          |
| down   | 17         |
| enter  | ?          |
| exit   | ?          |

## 16 - tcoupl_units_bis

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | units+**(settings)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| left   | 15         |
| enter  | ?          |
| exit   | ?          |

## 17 - tcoupl_sens

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **sens**+(settings) |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| right  | 18         |
| up     | 16         |
| down   | 19         |
| enter  | ?          |
| exit   | ?          |

## 18 - tcoupl_sens_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | sens+**(settings)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| left   | 17         |
| enter  | ?          |
| exit   | ?          |

## 19 - tcoulp_type

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **type**+(settings) |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| right  | 20         |
| up     | 17         |
| down   | 21         |
| enter  | ?          |
| exit   | ?          |

## 20 - tcoulp_type_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | type+**(settings)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| left   | 19         |

## 21 - tcoulp_junc

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **junc**+(settings) |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| right  | 22         |
| up     | 19         |
| down   | ?          |
| enter  | ?          |
| exit   | ?          |

## 22 - tcoulp_junc_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | junc+**(settings)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| left   | 11         |
| enter  | ?          |
| exit   | ?          |

## 23 - Lsync

### Variabili

| var     | state                 |
| ------- | --------------------- |
| display | linesync+**(on/off)** |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| enter  | ?          |
| exit   | ?          |
