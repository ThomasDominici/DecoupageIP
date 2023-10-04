# Challenge Quête Découpage de réseaux IP : 

Nous allons découper le réseau 172.16.1.0/24 en 4 sous réseaux de deux manières : symétrique et asymétrique.  

## 1. Découpage symétrique : 

Le plus gros sous-réseaux a besoin de 50 machines. Nous voulons donc 4 sous-réseaux symétriques avec un minimum de 50 machines.   
(2^6)-2 = 64 - 2 = **62** adresses disponibles pour chaque pôle informatique. Nous avons enlevé les 2 adresses réseau et de broadcast pour chaque sous-réseau.  

Le CIDR ici est 32 - 6 = **26**

Voici la répartition des adresses par pôle informatique :   

**A. Pôle informatique :**   
- Adresse de réseau : 172.16.1.0/26
- Adresse de début de plage : 172.16.1.1 
- Adresse de fin de plage : 172.16.1.62
- Adresse de broadcast : 17.16.1.63

**B. Pôle développement :** 
- Adresse de réseau : 17.16.1.64/26
- Adresse de début de plage : 17.16.1.65
- Adresse de fin de plage : 17.16.1.126
- Adresse de broadcast : 17.16.1.127

**C. Pôle administratif :**
- Adresse de réseau : 17.16.1.128/26
- Adresse de début de plage : 17.16.1.129
- Adresse de fin de plage : 17.16.1.190
- Adresse de broadcast : 17.16.1.191

**D. Pôle technicien :** 
- Adresse de réseau : 17.16.1.192/26
- Adresse de début de plage : 17.16.1.193
- Adresse de fin de plage : 17.16.1.254
- Adresse de broadcast : 17.16.1.255


## Découpage asymétrique : 

On va faire le même calcul mais pour chaque pôle en commençant par le plus gros et en finissant par le plus petit.  
- Pôle informatique : (2^6)-2 = 64 - 2 = **62** adresses disponibles. CIDR = 32-6=**26**.
- Pôle administratif : (2^5)-2 = 32 - 2 = **30** adresses disponibles. CIDR = 32-5=**27**.
- Pôle technicien : (2^5)-2 = 32 - 2 = **30** adresses disponibles. CIDR = 32-5=**27**.
- Pôle développement : (2^4)-2 = 16 - 2 = **14** adresses disponibles. CIDR = 32-4=**28**.

Nous aurons donc le découpage suivant : 

**A. Pôle informatique :**   
- Adresse de réseau : 17.16.1.0/26
- Adresse de début de plage : 17.16.1.1
- Adresse de fin de plage : 17.16.1.62
- Adresse de broadcast : 17.16.1.63

**B. Pôle administratif :**
- Adresse de réseau : 17.16.1.64/27
- Adresse de début de plage : 17.16.1.65
- Adresse de fin de plage : 17.16.1.94
- Adresse de broadcast : 17.16.1.95

**C. Pôle technicien :** 
- Adresse de réseau : 17.16.1.96/27
- Adresse de début de plage : 17.16.1.97
- Adresse de fin de plage : 17.16.1.126
- Adresse de broadcast : 17.16.1.127
- 
**D. Pôle développement :** 
- Adresse de réseau : 17.16.1.128/28
- Adresse de début de plage : 17.16.1.129
- Adresse de fin de plage : 17.16.1.142
- Adresse de broadcast : 17.16.1.143



  
