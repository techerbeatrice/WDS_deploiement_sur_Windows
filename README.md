# Déploiement de WDS sur Windows  

__

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/b89f5f50-df4e-4339-8e8d-8bfcfc69a62c)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/3b0a116e-2fd8-47d0-85b5-383b0796cc6f)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/44680d9f-ec69-4f2c-b9ed-9b2e28d272d4)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/9ce994cf-53b5-43b6-8dba-8481279e4e0f)

**Ne reconnait pas le format iso, mais wim**      

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/322ad814-418c-4437-a81d-8d4fa3c0eb83)

**Convertir l'image iso en format wim**      

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/99ea283d-0330-4b4f-a088-fd04e10ca968) 

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/c2c73483-8ad1-4718-814d-279a06033460)

Commandes à saisir dans le terminal de commande en mode administrateur pour la conversion iso en wim   

**dism /Get-WimInfo /WimFile:F:/sources/install.esd**     

**_dism /export-image /SourceImageFile:F:\sources\install.esd /SourceIndex:X /DestinationImageFile:C:\Users\Administrateur\Downloads\install.wim /Compress:max /CheckIntegrity_**     

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/5c877609-fd53-4171-a9f2-a51524b90c80)

**Convertir l'image install.esd en install.wim**  
le chiffre **1** correspond à **windows professionnel** donc remplacer X par 1    
L'exportation de l'image jusqu'à **100%** prend un certain temps      

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/f5d5b6ca-6d76-4484-8e09-1ef1d8e1a04d)

___

Reprise de l'opération **"ajout de l'image au format wim au serveur"**     

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/f547e3b5-53e9-4b12-9dc5-afc6f48d3ef6)
![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/028b60eb-50b0-4b9c-a219-0c93cfa89f90)
![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/511a950b-c96e-4893-86d7-ae1a7c486ff2)
![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/9528ec63-7be7-48c2-b9e2-44b6b0868b95)
![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/c9d7c151-9862-4cd7-8d31-8d6030ba641c)
![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/45955536-6e70-415f-87e2-968f1cf10429)

___

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/5faae3ac-43c3-4740-9c3c-adbda8988d21)

Accéder au **bios ou à l'uefi de la vm cliente** en faisant f12, del ou esc pour **modifier l'ordre de démarrage**     

une fois dans le bios ou dans l'uefi de la vm cliente, rechercher **'option de démarrage ou d'amorçage (boot)**      
modifier l'ordre de démarrage pour que le **démarrage réseau (PXE boot)** soit **la première option**, pour ce faire déplacer **PXE en haut** de la liste   
pour qu'elle soit **rioritaire**   
**enregistrer** le changement et quitter le bios ou l'uefi
**redémarrer** la vm 
la vm démarre cette fois-ci à partir du réseau, saisir les informations d'identifation pour qu'elle **se connecte au serveur WDS**  
pour le nom de domaine, utiliser le nom du serveur WDS c'est-à-dire **srv-wds** et pour le compte d'utilisateur, utiliser **le compte d'administration**     

une fois connecté, une liste d'images windows disponibles sur le serveur WDS apparaît, **choisisser l'image** que vous souhaitez déployer sur la vm cliente   


