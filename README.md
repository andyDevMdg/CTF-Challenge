# root-me :skull:
Vous trouverez ici comment résoudre certains challenges du site.

## FTP - Authentification
Un échange authentifié de fichier réalisé grâce au protocole FTP. Retrouvez le mot de passe utilisé par l’utilisateur.

- Démarrer le challenge: un fichier nommée **_ch1.pcap_** sera téléchargé automatiquement
- ouvrir **_ch1.pcap_** aver Wireshark

- rechercher **_ftp_** car il s'agit d'un **_protocole FTP_**

- dans la colonne **"info"**, une ligne contient **"Request: PASS"** et le mot de passe s'y trouve

- voilà pour ce challenge


## TELNET - authentification
Retrouvez le mot de passe de l’utilisateur dans cette capture réseau de session TELNET.

- Démarrer le challenge: un fichier nommée **_ch2.pcap_** sera téléchargé automatiquement
- ouvrir **_ch2.pcap_** aver Wireshark

- faire un clic-droit sur un des paquets > follow > tcp stream

- le mot de passe devrait s'afficher dans boîte de dialogue qui s'affiche


## Authentification twitter
