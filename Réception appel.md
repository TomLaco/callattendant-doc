# Gestion des appels entrants
Il existe 3 configurations de bloquage possible pour chaque ligne dans l'application.
```mermaid
flowchart LR

M{Mode de bloquage}
M --> LB[Liste blanche seule]
M --> LB+N[Liste blanche puis liste noire]
M --> LN[Liste noire seule]
```
## Filtrage liste blanche
```mermaid
flowchart LR
N[Num&eacutero entrant] --> LB{Est dans la liste blanche}
LB -->|oui| P[T&eacutel&eacutephone]
LB -->|non| R[R&eacutepondeur]
```
## Filtrage liste noire
```mermaid
flowchart LR
N[Num&eacutero entrant] --> LN{Est dans la liste noire}
LN -->|oui| R[R&eacutepondeur]
LN -->|non| AI{Recherche annuaire inverse}
AI -->|est ind&eacutesirable| R
AI -->|sinon| T[T&eacutel&eacutephone]
```
## Fitrage liste blanche puis liste noire
```mermaid
flowchart LR
N[Num&eacutero entrant] --> LB{Est dans la liste blanche}
LB -->|oui| T[T&eacutel&eacutephone]
LB -->|non| LN{Est dans la liste noire}
LN -->|non| AI{Recherche annuaire inverse}
AI -->|est ind&eacutesirable| R[R&eacutepondeur]
AI -->|sinon| T[T&eacutel&eacutephone]
LN -->|oui| R
```

