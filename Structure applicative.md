# Structure applicative du projet
```mermaid
mindmap
((CallAttendant))
    {{Service}}
      filtrage
      répondeur
    {{Serveur web}}
      configuration
      consultation
        messagerie vocale
        liste des appels reçus
    {{IHM}}
      afficheur
        appel en cours
        messagerie vocale
      boutons
        ajouter numéro à la liste noire
        lire messages vocaux
    {{Connecteurs}}
      réseau
      entrée ligne
      sortie téléphone
```