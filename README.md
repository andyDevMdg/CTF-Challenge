# root-me :skull: (work-in-progress)
Vous trouverez ici comment résoudre certains challenges du site.

## FTP - Authentification
Un échange authentifié de fichier réalisé grâce au protocole FTP. Retrouvez le mot de passe utilisé par l’utilisateur.

- "Démarrer le challenge": un fichier nommée **_ch1.pcap_** sera téléchargé automatiquement
- ouvrir **_ch1.pcap_** aver Wireshark

![](/ss_00001.png)

- rechercher **_ftp_** car il s'agit d'un **protocole FTP**

![](/ss_00002.png)

- dans la colonne **"info"**, une ligne contient **"Request: PASS"** et le mot de passe s'y trouve

![](/ss_00003.png)

- voilà pour ce challenge


## TELNET - authentification
Retrouvez le mot de passe de l’utilisateur dans cette capture réseau de session TELNET.

- "Démarrer le challenge": un fichier nommée **_ch2.pcap_** sera téléchargé automatiquement
- ouvrir **_ch2.pcap_** aver Wireshark

![](/ss_00004.png)

- faire un clic-droit sur un des paquets > follow > tcp stream

![](/ss_00005.png)

- le mot de passe devrait s'afficher dans boîte de dialogue qui s'affiche

![](/ss_00006.png)

## Authentification twitter
Une session d’authentification twitter a été capturée. Retrouvez le mot de passe de l’utilisateur dans cette capture réseau.

- "Démarrer le challenge": un fichier nommée **_ch3.pcap_** sera téléchargé automatiquement
- ouvrir **_ch3.pcap_** aver Wireshark

![](/ss_00007.png)

- On peut voir qu'il s'agit d'un protocole HTTP
- Faire un clic-droit sur le paquet > follow > HTTP stream

![](/ss_00008.png)

- Puisqu'il s'agit d'une Authentification HTTP, _les identifiants_ devrait se trouver sur la ligne **"Authorization"**

![](/ss_00009.png)

- On peut voir **"Basic"_* suivi d'une chaîne de caractère en **base64** qu'il faudra decoder pour avoir le mot de passe

## ETHERNET - trame
Retrouvez les données normalement confidentielles contenues dans cette trame.

-"Démarrer le challenge": vous obtiendrez un fichier **_ch12.txt_**
- Ce fichier contient une trame ethernet qu'il faudra décodé

![](/ss_000010.png)

- Utiliser n'importe quel **"packet decoder"** que vous trouverez en ligne
- Vous devrer avoir le resultat suivant

![](/ss_000011.png)

- On pourra constater qu'il s'agit d'un protocole HTTP donc _les identifiants_ se trouvent dans **"Authorization"**

![](/ss_00012.png)

- Pas la peine de decoder la chaîne de caracère en **base64**, le mot de passe est visible

## Bluetooth - Fichier inconnu
Votre ami travaillant à l’ANSSI a récupéré un fichier illisible dans l’ordi d’un hacker. Tout ce qu’il sait est que cela provient d’un échange entre un ordinateur et un téléphone. A vous d’en apprendre le plus possible sur ce téléphone.

La réponse est le hash SHA1 de la concaténation de l’adresse MAC (en majuscules) et du nom du téléphone.

Exemple :
AB:CD:EF:12:34:56monTelephone -> 836eca0d42f34291c5fefe91010873008b53c129

-"Démarrer le challenge": vous obtiendrez un fichier **_ch18.bin_**
- Ouvrir le fichier .bin sur Wireshark, on y trouvera plusieurs paquets

![](/ss_000013.png)

- Dans la liste des paquets, trouver celui contenant **"Remote name Request complete"** dans ses infos

![](/ss_000014.png)

- Puis regarder dans la fenêtre des détails du paquet, dans **"Bluetooth HCI Event"** les termes **"BD_ADDR"** et **"Remote Name"**

![](/ss_000015.png)

- **"BD_ADDR"** indique le _Bluetooth Address_ de l'ordinateur
- **"Remote Name"** indique le nome du téléphone
- Une fois ces deux informations obtenus, mettre en majuscule le _Bluetooth Adresss_, les concatener et les chiffrer en SHA1 sur un site pour obtenir le mot de passe

