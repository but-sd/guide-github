Github Projects est une fonctionnalité de GitHub qui permet de gérer des tâches à réaliser. Il est possible de créer des colonnes et des cartes. Les cartes peuvent être déplacées d'une colonne à une autre. Il est possible d'assigner une personne à une carte. Il est possible de créer des cartes à partir d'issues ou de pull requests.

## Backlog

Github Projects propose différents templates de colonnes. Le template `Backlog` permet de gérer de manière agile.

Le backlog est une liste de tâches à réaliser. Les tâches sont triées par priorité. 

### Colonne `New`

La colonne `New` contient les tâches à réaliser. Elle contient les tâches à réaliser dans le futur. Elles ne sont pas encore totalement spécifiées.

Le Product Owner peut ajouter des tâches dans cette colonne. Il peut aussi modifier les tâches existantes.

### Colonne `Backlog`

Pour passer un ticket de la colonne `New` à la colonne `Backlog`, il faut que le ticket soit spécifié, estimé et priorisé. 

La spécification est généralement faite par le Product Owner. Une fois que le ticket est spécifié, il est possible de l'estimer. Cela se fait généralement par l'équipe de développement durant une cérémonie de planification, c'est le moment pour échanger sur le ticket, pour le comprendre et pour l'estimer. 

Si durant la cérémonie de planification, le ticket est jugé trop complexe, il est possible de le découper en plusieurs tickets. Certains tickets peuvent aussi être fusionnés, si ils sont trop petits. On peut aussi ajouter des tickets dans la colonne `New` si on se rend compte qu'il manque des tickets ou même supprimer des tickets si on se rend compte qu'ils ne sont pas nécessaires.

Une fois que le ticket est estimé, il est possible de le prioriser. Cela se fait généralement par le Product Owner.

Pour la spécification, on peut utiliser sur un template de ticket. Par exemple, on peut partir sur le template suivant :

```markdown
# Objectif

**En tant que**, _personna_ 
**Je souhaite**, _quoi_
**Afin de**, _pourquoi_

# Critère d'acceptation
**Etant donné que**,  _situation actuelle_
**Lorsque**, _objectif du ticket_
**Alors**, _résultat souhaité_

# Pré-requis
_Ce qui est nécessaire pour afin de réaliser le ticket_

# DOD

_Définition Of Done_ 
```

`En tant que` permet de définir la personne qui souhaite réaliser l'action, de comprendre le contexte de l'action, de comprendre les motivations de la personne, les enjeux de l'action.

`Je souhaite` permet de définir l'action à réaliser. C'est l'action qui sera réalisée par la personne.

`Afin de` permet de définir le but de l'action. C'est le résultat attendu par la personne.

`Etant donné que` permet de définir le contexte de l'action. C'est la situation actuelle.

`Lorsque` permet de définir l'action à réaliser. C'est l'action qui sera réalisée par la personne.

`Alors` permet de définir le résultat attendu par la personne.

`Pré-requis` permet de définir les pré-requis pour réaliser le ticket. Par exemple la réalisation d'un autre ticket.

`Définition Of Done` permet de définir les critères de fin de réalisation du ticket. C'est la définition de fini. Par exemple, le code est testé, le code est documenté, le code est déployé.

### Colonne `Ready`

Une fois le ticket spécifié, estimé et priorisé, il est possible de le passer dans la colonne `Ready`. Cela signifie que le ticket est prêt à être réalisé.

Les membres de l'équipe peuvent prendre un ticket dans la colonne `Ready`, c'est le moment de transformer le ticket en `issue` rattacher à un repository. Pour plus d'information sur les `issues`, voir la section [Issues](./issues.md).

### Colonne `In progress`

Une fois le ticket pris par un membre de l'équipe, il est possible de le passer dans la colonne `In progress`. Cela signifie que le ticket est en cours de réalisation.

### Colonne `In review`

Une fois le ticket réalisé, il est possible de le passer dans la colonne `In review`. Cela signifie que le ticket est en cours de revue, généralement grâce à une pull request.

### Colonne `Done`

Une fois le ticket revu, il est possible de le passer dans la colonne `Done`. Cela signifie que le ticket est terminé.

## By priority

Le template `By priority` permet de gérer les tâches à réaliser par priorité.

Les tickets sont triés par priorité. Les tickets les plus prioritaires sont en haut de la colonne. Les tickets les moins prioritaires sont en bas de la colonne.

L'équipe de développeur est sensée prendre les tickets les plus prioritaires en premier.

## By size

Le template `By size` permet de gérer les tâches à réaliser par taille.