# root-me :skull:
Vous trouverez ici comment résoudre certains challenges du site.

## FTP - Authentification
Un échange authentifié de fichier réalisé grâce au protocole FTP. Retrouvez le mot de passe utilisé par l’utilisateur.

- "Démarrer le challenge": un fichier nommée **_ch1.pcap_** sera téléchargé automatiquement
- ouvrir **_ch1.pcap_** aver Wireshark
(screenshot)
- rechercher **_ftp_** car il s'agit d'un **_protocole FTP_**
(screenshot)
- dans la colonne **"info"**, une ligne contient **"Request: PASS"** et le mot de passe s'y trouve
(screenshot)
- voilà pour ce challenge


## TELNET - authentification
Retrouvez le mot de passe de l’utilisateur dans cette capture réseau de session TELNET.

- "Démarrer le challenge": un fichier nommée **_ch2.pcap_** sera téléchargé automatiquement
- ouvrir **_ch2.pcap_** aver Wireshark
(screenshot)
- faire un clic-droit sur un des paquets > follow > tcp stream
(screenshot)
- le mot de passe devrait s'afficher dans boîte de dialogue qui s'affiche
(screenshot)

## Authentification twitter
Une session d’authentification twitter a été capturée. Retrouvez le mot de passe de l’utilisateur dans cette capture réseau.

- "Démarrer le challenge": un fichier nommée **_ch3.pcap_** sera téléchargé automatiquement
- ouvrir **_ch3.pcap_** aver Wireshark
(screenshot)
- On peut voir qu'il s'agit d'un protocole HTTP
- Faire un clic-droit sur le paquet > follow > HTTP stream
(screenshot)
- Puisqu'il s'agit d'une Authentification HTTP, les identifiants devrait se trouver sur la ligne **"Authorization"**
- On peut voir **_"Basic"_** suivi d'une chaîne de caractère en **base64** qu'il faudra decoder pour avoir le mot de passe

## ETHERNET - trame
