1. Lors de l'utilisation de Vuex, l'¨¦tat (`state`) doit ¨ºtre plac¨¦ dans les propri¨¦t¨¦s calcul¨¦es.

2. Vuex semble s'ex¨¦cuter avant l'initialisation du composant. Cela signifie que vous ne pouvez pas utiliser quelque chose comme  
   `...mapMutations([this.selectedColor])`  
   pour changer ce que vous voulez s¨¦lectionner.

3. Utiliser `ref` pour obtenir le n?ud racine d'un composant (le premier tag sous le template) semble inutile, car il est impossible de manipuler directement le n?ud racine ou d'obtenir ses styles.  
   - Vous pouvez utiliser `this.$el` pour obtenir la structure DOM du n?ud racine du composant.  
   - **Note (27/03)** : Lorsque `ref` est utilis¨¦ sur un ¨¦l¨¦ment DOM, il renvoie un objet DOM. Lorsqu'il est utilis¨¦ sur un composant Vue, il renvoie un objet VueComponent, dont la propri¨¦t¨¦ `$el` correspond au n?ud racine DOM de ce composant.

4. Lors de l'utilisation de minuteurs, utilisez des fonctions fl¨¦ch¨¦es pour que `this` pointe vers le composant Vue (le `this` dans une fonction normale change en fonction de celui qui l'appelle, tandis que la fonction `setInterval()` appartient ¨¤ l'objet `window`).

5. Les ¨¦v¨¦nements clavier comme `keyUp` et `keyDown` semblent uniquement pouvoir ¨ºtre attach¨¦s ¨¤ des objets `document` ou ¨¤ des ¨¦l¨¦ments capables de recevoir le focus, comme les champs de saisie (`input`).

6. Les mutations de Vuex ne peuvent pas directement accepter un second param¨¨tre. Il est n¨¦cessaire d'utiliser un objet ou un tableau pour transmettre plusieurs param¨¨tres.

7. Comment impl¨¦menter des raccourcis clavier :  
   - Utilisez des fonctions fl¨¦ch¨¦es pour que `this` pointe vers le composant, permettant ainsi aux fonctions internes d'¨ºtre appel¨¦es depuis l'ext¨¦rieur.  
   - Utilisez le `store` pour sauvegarder la correspondance entre les touches et les fonctions.  
   - Cr¨¦ez un composant d¨¦di¨¦ qui ¨¦coute les ¨¦v¨¦nements clavier sur `document` et ex¨¦cute les fonctions appropri¨¦es en fonction des correspondances d¨¦finies dans le `store`.

8. Un `watcher` dans Vue peut se d¨¦clencher lui-m¨ºme.

9. Toujours ¨¤ propos des `watchers` : Lorsqu'un `watcher` surveille une donn¨¦e li¨¦e bidirectionnellement et modifie cette donn¨¦e, il peut arriver que les donn¨¦es du DOM ne soient pas mises ¨¤ jour correctement (cela pourrait ¨ºtre d? ¨¤ Vuetify). Une solution consiste ¨¤ utiliser `setTimeout` pour retarder de 1 ms la modification des donn¨¦es.

10. Le syst¨¨me de grille de Vuetify contient un bug qui peut provoquer une erreur dans le nombre de colonnes occup¨¦es par un ¨¦l¨¦ment (`col`). Une solution consiste ¨¤ r¨¦initialiser la propri¨¦t¨¦ `flex-basis` de chaque ¨¦l¨¦ment `col` ¨¤ `auto` :  
    ```css
    .col {
        flex-basis: auto;
    }
    ```

11. L'objet `this.$vuetify.breakpoint` de Vuetify n'est pas mis ¨¤ jour instantan¨¦ment. Il y a un d¨¦lai apr¨¨s le redimensionnement de la fen¨ºtre du navigateur avant qu'il ne soit mis ¨¤ jour.

12. Les probl¨¨mes de mise en cache peuvent ¨ºtre r¨¦solus en ajoutant un param¨¨tre al¨¦atoire ¨¤ chaque requ¨ºte, par exemple `'?rand=' + Math.random`.
