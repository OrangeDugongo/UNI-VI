# Stati

## 0 - ch1

### Variabili

| var    | state |
| ------ | ----- |
| chan   | 1     |
| auto   | on    |
| rate   | slow  |
| filter | on    |
|rel        | off |
|unità | query? |
|shift | off |
|display |  |

### Passaggi di stato

| button | next state                                   |
| ------ | -------------------------------------------- |
| DCV2   | 2                                            |
| shift  | 1                                            |
| rel    | 0: rel -> !rel                               |
| filt   | 0: filter --> !filter                        |
| up     | 0: unità --> query?x10<br />    auto --> off |
| down   | 0: unità --> query?:10<br />    auto --> off |
| auto   | 0: auto --> on                               |
| rate   | 0: rate --> rate++                           |
| digits | display --> display++                        |
| temp1  | 4                                            |
| temp2  | 6                                            |
| v1/v2  | 8                                            |
| step   | 9                                            |
| scan   | 10                                           |

## 1 - ch1_shift

### Variabili

| var    | state |
| ------ | ----- |
| chan   | 1   |
| auto   | on    |
| rate   | rate |
| filter | on    |
|rel        | off |
|unità | query? |
|shift | on |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| v1-v2  | 11         |
| type   | 12         |
| tcoupl | 17         |

## 2 - ch2

### Variabili

| var    | state |
| ------ | ----- |
| chan   | 2    |
| auto   | on    |
| rate   | rate |
| filter | on    |
|rel        | off |
|unità | query? |
|shift | off |

## 3 - ch2_shift

### Variabili

| var    | state |
| ------ | ----- |
| chan   | 2    |
| auto   | on    |
| rate   | rate |
| filter | on    |
|rel        | off |
|unità | query? |
|shift | on |

### Passaggi di stato

| button | next state |
| ------ | ---------- |
| v1-v2  | 11         |
| type   | 12         |
| tcoupl | 17         |

## 4 - temp1

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1      |
| rate   | rate   |
| filter | on     |
| unità  | query? |
| shift  | off    |

## 5 - temp1_shift

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1      |
| rate   | rate   |
| filter | on     |
| unità  | query? |
| shift  | off    |

## 6 - temp2

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 2      |
| rate   | rate   |
| filter | on     |
| unità  | query? |
| shift  | off    |

## 7 - temp2_shift

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 2      |
| rate   | rate |
| filter | on     |
| unità  | query? |
| shift  | on    |

## 8 - v1/v2

### Variabili

| var     | state |
| ------- | ----- |
| chan    | 1-2   |
| rate    | rate  |
| auto    | on    |
| display | RA    |

## 9 - step

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1     |
| filter | filter |
| rate   | rate |
| auto | on |
| unità  | query? |
| shift  | off |
| step | step |

## 10 - scan

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1     |
| filter | filter |
| rel | rel |
| rate   | rate |
| auto | on |
| unità  | query? |
| shift  | off |
| scan | scan |

## 11 - v1-v2

### Variabili

| var    | state  |
| ------ | ------ |
| chan   | 1     |
| rate | rate |
| filter | filter |
| rel | rel |
| auto | on |
| display | d |

## 12 - type_analog

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **analog**+(on/off) |

## 13 - type_analog_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | analog+**(on/off)** |

## 14 - type_digital

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | **digital**+(on/off) |

## 15 - type_digital_bis

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | digital+**(on/off)** |

## 16 - type_window

### Variabili

| var     | state                 |
| ------- | --------------------- |
| chan    | chan                  |
| display | window+**(settings)** |

## 17 - tcoupl_units

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | **units**+(settings) |

## 18 - tcoupl_units_bis

### Variabili

| var     | state                |
| ------- | -------------------- |
| chan    | chan                 |
| display | units+**(settings)** |

## 19 - tcoupl_sens

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **sens**+(settings) |

## 20 - tcoupl_sens_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | sens+**(settings)** |

## 21 - tcoulp_type

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **type**+(settings) |

## 22 - tcoulp_type_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | type+**(settings)** |

## 23 - tcoulp_junc

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | **junc**+(settings) |

## 24 - tcoulp_junc_bis

### Variabili

| var     | state               |
| ------- | ------------------- |
| chan    | chan                |
| display | junc+**(settings)** |
