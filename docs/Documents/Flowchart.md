# Flödesschema

- Ett flödesschema är en typ av diagram som representerar ett arbetsflöde eller en process. 
- Ett flödesschema kan beskrivas som en algoritm i diagramform, det vill säga en steg-för-steg-process för att lösa en uppgift.
- Flödesschema visar stegen som noder med olika form och deras ordning genom att koppla ihop noderna med pilar. 
- Ett flödesschema illustrerar en lösningsmodell för ett givet problem. 



## Noder

Ett flödesschema består av olika **Noder** som representerar olika typer av steg i processen. De vanligaste symbolerna är:

``` mermaid
graph TD
Start([Start/End])
Input[/Input/Output/]
Process[Process]
Decision{Decision}
```
## Flöde

**Pilarna** i flödesschemat visar riktningen på flödet mellan noderna.
``` mermaid
graph TD
Start([Start])-->End([End])
```
## Input och Output i flödesschema
Input/Output i flödesschema representeras av en **parallellogram** som används för att visa att programmet tar emot data från användaren eller skriver ut data till användaren.

Exempel på ett flödesschema som illustrerar **Input** och **Output**, flödesschemat visar ett program som tar emot ett namn från användaren och skriver ut det på skärmen:
```mermaid
graph TD
Start([Start])-->Input[/Input name/]
Input-->Output[/Output name/]
Output-->End([End])
```

## Selektion i flödesschema
Selektion i flödesschema representeras av en **decision-nod** som har två eller flera utgångar. Decision-noden används för att visa att programmet kan ta olika vägar beroende på ett villkor. Texten i pilarna 

---
Exempel på ett flödesschema som illustrerar en **if-sats**, om villkoret är sant körs processen:
``` mermaid
graph TD
Start([Start])-->Decision{Decision?}
Decision-->|Yes|Process[This process runs]
Decision-->|No|End([End])
Process-->End
```

---
Exempel på ett flödesschema som illustrerar en **if och else-sats**, om villkoret är sant körs den första processen, annars körs den andra processen:
``` mermaid
graph TD
Start([Start])-->Decision{Decision?}
Decision-->|Yes|Process1[This process runs]
Decision-->|No|Process2[This process runs]
Process1-->End([End])
Process2-->End
```

---
Exempel på ett flödesschema som illustrerar en **if och elif-sats**, om villkoret är sant körs den första processen, annars kontrolleras nästa villkor och om det är sant körs den andra processen:
``` mermaid
graph TD
Start([Start])-->Decision{Number?}
Decision-->|1|Process1[This process runs]
Decision-->|2|Process2[This process runs]
Decision-->|All other numbers|End([End])
Process1-->End
Process2-->End
```

---
Exempel på ett flödesschema som illustrerar en **if, elif och else-sats**, om villkoret är sant körs den första processen, annars kontrolleras nästa villkor och om det är sant körs den andra processen, annars körs den tredje processen:
``` mermaid
graph TD
Start([Start])-->Decision{Number?}
Decision-->|1|Process1[This process runs]
Decision-->|2|Process2[This process runs]
Decision-->|All other numbers|Process3[This process runs]
Process1-->End([End])
Process2-->End
Process3-->End
```
## Iteration i flödesschema
Iteration i flödesschema representeras av en **loop** som har en utgång som leder tillbaka till en tidigare nod. Loopen används för att visa att programmet kan upprepa vissa steg beroende på ett villkor. Texten i pilarna visar villkoret som avgör om loopen ska fortsätta eller avslutas.

Exempel på ett flödesschema som illustrerar en **loop**, decision-noden utgör en loop då den har en utgång som leder tillbaka till sig själv:
``` mermaid
graph TD
Start([Start])-->Decision{Condition?}
Decision-->|Yes|Process[This process iterates]
Process-->Decision
Decision-->|No|End([End])
```

