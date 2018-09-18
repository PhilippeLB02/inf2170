; ************************************************************
;       Programme: PREMIER3.TXT     version PEP813 sous Windows
;
;       version 3: version finale qui traite les débordements et qui demande la réexécution
;
;       Mon premier programme qui affiche la somme de 2 nombres signés.
;
;       auteur:   Bernard Martin
;       courriel: martin.bernard@uqam.ca
;       date:     hiver 2018
;       cours:    INF2170
; ***********************************************************
;
         STRO    bienvenu,d  ; message réel "Bienvenue" avec un e car les symboles sont limitées à 8 caractères
;
début:   STRO    demande1,d  ; premier nombre demandé
         DECI    nombre1,d   ; lecture du premier nombre
         BREQ    fini        ; le nombre 0 déclenche la fin du programme
         BRV     débordem    ; il y a débordement si le nombre est > 32767 ou < -32768
         STRO    demande2,d  ; deuxième nombre demandé
         DECI    nombre2,d   ; lecture du deuxième nombre
         BRV     débordem    ; il y a débordement si le nombre est > 32767 ou < -32768
         LDA     nombre1,d   ; premier nombre à traiter
         ADDA    nombre2,d   ; premier nombre + deuxième nombre
         BRV     débordem    ; il y a débordement si la somme est > 32767 ou < -32768
         STA     total,d     ; conservons le résultat
         STRO    réponse,d   ; affichage des résultats
         DECO    total,d     ; affiche le total en décimal
         CHARO   '.',i       ; fin de la phrase
         BR      début       ; recommençons le processus
;
débordem:STRO    déborde,d   ; message de débordement, soit > 32767 (ou < -32768)
correct: BR      début       ; recommençons le processus
;
fini:    STRO    termine,d   ; affichage de fin normale
         STOP
;
nombre1: .BLOCK  2           ; #2d valeur initiale zéro
nombre2: .BLOCK  2           ; #2d valeur initiale zéro
total:   .BLOCK  2           ; #2d valeur initiale zéro
;
bienvenu:.ASCII  "Bienvenue à ce programme d'additions de 2 nombres."
         .ASCII  "\nVous devrez entrer 2 nombres compris entre -32768 et 32767."
         .ASCII  "\n\nPour terminer le programme, veuillez entrer le chiffre 0 comme premier nombre.\x00"
demande1:.ASCII  "\n\n\nVeuillez entrer le premier nombre (0-pour terminer): \x00"; précédé de 3 changements de ligne
demande2:.ASCII  "\nVeuillez entrer le deuxième nombre: \x00"
réponse: .ASCII  "\nLe total de ces 2 nombres est \x00"
déborde: .ASCII  "\nLe total excède le minimum(-32768) ou le maximum permis(32767).\x00"
termine: .ASCII  "\n\nFin normale du programme.\x00"
         .END  
