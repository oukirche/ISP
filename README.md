# ISP
## Interface Segregation Principle
La ségrégation signifie garder les choses séparées, 
et le principe de ségrégation des interfaces consiste à séparer les interfaces.
Le principe stipule que de nombreuses interfaces spécifiques au client valent 
mieux qu'une interface à usage général. Les clients ne doivent pas être contraints
d'implémenter une fonction dont ils n'ont pas besoin.
### Exemple
Dans cet exemple, nous allons créer un système pour gérer une station de véhicules.
Donc on a 5 method principales
* parkCar()
* unparkCar()
* getCapacity()
* calculateFee(Car car)
* doPayment(Car car)
#### Probleme
Considérons maintenant que nous voulons mettre en place un parking gratuit.
Donc on tombe sur le probleme qu'il faut implementer les deux method de payement
calculateFee(Car car) et doPayment(Car car)
#### Solution
Notre interface de parking était composée de 2 éléments : la logique de stationnement (garer la voiture, la libérer, obtenir la capacité) et la logique de paiement.
Mais c'est trop spécifique.<br> Pour cette raison, notre classe FreeParking a été forcée d'implémenter des méthodes liées au paiement qui ne sont pas pertinentes. Séparons ou séparons les interfaces.
Donc dans notre solution on a ajouter deux autre interfaces qui hérite de l'interface ParkingLot<br>
La premiere : FreeParkingLot : pour la logique de stationnement pour les Parking gratuit
La deusieme : PaidParkingLot : pour la logique de stationnement + la logique de payement