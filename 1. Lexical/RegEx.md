### Definition
___
- Describe regular sets of strings
- Symbols other than ( ) | * stand for themselves
- Use ∈ for an empty string
- Concatenation α β = fist part matches α, second part matches β
- Union α | β = α or β
- Kleene star α* = 0 or more matches of α
- Use ( ) for grouping

### Notations
---
- α+ = one or more (i.e. αα∗) 
- α? = 0 or 1 (i.e. (α| ∈)) 
- \[xyz\]= x|y|z 
- \[x-y\]= all characters from x to y, e.g. \[0-9\] = all ASCII digits 
- \[^x-y\]= all characters other than \[x-y\] 
- . matches any character

### Examples
---
- (0|1|2|3|4) => \[0-4\] 
- (a|g|h|m) => \[aghm\] 
- (0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)* => \[0-9\]+ 
- (E|e)(+|-|∈)(0|1|2|3|4|5|6|7|8|9)+ => \[Ee\]\[+-\]?\[0-9\]+