# LAB-4-Analyse-statique-d-un-APK-avec-JADX-GUI-dex2jar-JD-GUI
1. Vérification du format de l’APK

Dans un premier temps, une vérification a été effectuée afin de confirmer que le fichier APK est bien une archive au format ZIP.
Cette étape permet de s’assurer que le fichier peut être décompressé et analysé à l’aide d’outils standards.

2. Inspection du contenu de l’APK

Le contenu de l’APK a été listé afin d’identifier les différents éléments qui le composent, notamment :

les fichiers DEX (Dalvik Executable),
les ressources (images, layouts),
les fichiers de configuration (AndroidManifest.xml).

Cette étape est essentielle pour comprendre la structure globale de l’application.

3. Analyse statique avec JADX GUI

Une analyse statique a été réalisée à l’aide de l’outil JADX GUI, permettant de :

décompiler les fichiers DEX en code Java lisible,
explorer l’architecture de l’application,
identifier les classes et méthodes critiques.
4. Recherche de chaînes sensibles

Une recherche approfondie de chaînes de caractères sensibles a été effectuée dans le code décompilé.
Cette analyse a permis de détecter des informations potentiellement critiques, telles que :

des clés de chiffrement,
des identifiants ou constantes sensibles.
5. Identification d’une clé AES

L’analyse a révélé la présence d’une clé de chiffrement AES intégrée dans l’application.
Cela représente une faiblesse de sécurité, car une clé embarquée dans le code peut être extraite par rétro-ingénierie.
<img width="1836" height="912" alt="image" src="https://github.com/user-attachments/assets/4f084b03-2b25-4804-846b-e08b9a014ef5" />

6. Déchiffrement du secret

En utilisant la clé AES identifiée, une opération de déchiffrement a été réalisée.
Cette étape a permis de récupérer la valeur suivante :

Code obtenu :
i want to believe

<img width="1378" height="725" alt="image" src="https://github.com/user-attachments/assets/7abc4996-f2f6-43a8-a360-f0848b40b9e0" />

7. Conversion DEX vers JAR

Enfin, les fichiers DEX ont été convertis en fichiers JAR à l’aide de l’outil dex2jar.
Cette conversion facilite l’analyse avec d’autres outils Java et permet une inspection plus approfondie du code.




<img width="1376" height="768" alt="U4nJKciH" src="https://github.com/user-attachments/assets/965eecca-a977-4d07-b4fa-7da2957233d9" />

Conclusion

Cette analyse met en évidence plusieurs points importants :

L’application contient des données sensibles directement intégrées dans le code.
L’utilisation d’une clé AES en clair constitue une vulnérabilité critique.
Les outils de rétro-ingénierie permettent facilement d’extraire et d’exploiter ces informations.

Des mesures de sécurité supplémentaires sont recommandées, notamment :

l’utilisation de mécanismes de gestion sécurisée des clés,
l’obfuscation du code,
et le stockage sécurisé des données sensibles.
