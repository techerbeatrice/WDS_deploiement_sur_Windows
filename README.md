# Déploiement de WDS sur Windows  

__

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/b89f5f50-df4e-4339-8e8d-8bfcfc69a62c)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/3b0a116e-2fd8-47d0-85b5-383b0796cc6f)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/44680d9f-ec69-4f2c-b9ed-9b2e28d272d4)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/9ce994cf-53b5-43b6-8dba-8481279e4e0f)

**Ne reconnait pas le format iso, mais wim**      

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/322ad814-418c-4437-a81d-8d4fa3c0eb83)

**Convertir l'image iso en format winm**      

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/99ea283d-0330-4b4f-a088-fd04e10ca968)

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/bd0f0b88-1a39-4a88-b46b-b764298504d2)

Commandes à saisir dans le terminal de commande en mode administrateur pour la conversion iso en wim   

dism /Get-WimInfo /WimFile:F:/sources/install.esd   

dism /export-image /SourceImageFile:D:\sources\install.esd /SourceIndex:X /DestinationImageFile:C:\Users\Administrateur\Downloads\install.wim /Compress:max /CheckIntegrity   

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/5c877609-fd53-4171-a9f2-a51524b90c80)

Convertir l'image install.esd en install.wim  
le chiffre 1 correspond à windows professionnel   

![image](https://github.com/techerbeatrice/WDS_deploiement_sur_Windows/assets/138071140/f5d5b6ca-6d76-4484-8e09-1ef1d8e1a04d)





