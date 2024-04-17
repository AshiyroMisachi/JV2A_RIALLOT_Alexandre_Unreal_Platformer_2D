JV2A Riallot Alexandre

J'ai choisi comme feature variantes UI et Animation

Pour le processus, j'ai commencé par toucher au BP_ThirdPersonCharacter pour retirer les controles forward et backward ainsi que le movement de la caméra. Pour ensuite créer un nouveau Level, j'ai ensuite réalisé en premier temps un BP pour les trous
avec une simple box collider qui appele une fonction du player controller que j'avais créé auparavant restartant le level. 
Ensuite j'ai  créé deux BP quasiment identiques pour les collectibles sans héritages car j'ai oublié, pour la vie et le score appelant une fonction du player controller puis détruisant le collectible.
Ensuite venu les pièges, des mesh que j'ai passé en overlap du à des soucis de double appel du hitCollider, en overlapant le joueur perd un point de vie avec une fonction du player controller et le joueur est téléporté sur un transform venant d'un scene component.

Après j'ai démarré l'UI en créant un Widget plaçant une progress bar pour la vie et un horizontal box pour les textes du score. J'ai donc fait deux fonctions pour les updates que j'ai placé dans les fonctions du player controller qui modifiait la vie et le score.
Par la suite je suis allé sur Mixamo pour récupérer des animations. Pour ensuite faire un Blend Space 1D où mettre mes animations de courses, j'ai donc modifié le BS du ThirdPersonCharacter et son mesh. Ensuite j'ai réalisé un ABP pour y mettre mon BS en gérant 
la speed du BS dans l'event graph du ABP. Probleme étant que l'animation de marche ne se voyait pas, très certainement car la vélocité du player augmentait trop vite. J'ai donc ajouté d'autres animations avec un StateMachine avec une dance sur E et un saut un peu bancale.
