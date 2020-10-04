# Introduction:
Pendant bien des années, le transport de la voix et celui des données se faisait de manière distincte au sein des entreprises.
Pour le transport de la voix il fallait recourir au réseau téléphonique et pour les données recourir au réseau informatique. 
Bien entendu cet état de chose n’était pas sans conséquences. En effet, les entreprises étaient confrontées à des problèmes tels :
les budgets et dépenses en télécoms de plus en plus élevés, la perte de la bande passante allouée à une communication
qui n’a pu être établie (gestion non rationnelle de la bande passante), affectation d’un intervalle de temps (IT)à un canal voie ou données,
échec de l’intégration des services de transport de données dans les PABX pour ne citer que ceux-là.

# Comment ca marche :
1. l'utilisateur enregistre dans le système et faire le paiement nécessaire.
2. le système génère une id unique pour l'utilisateur.
3. l'utilisateur télécharge deux applications mobiles, la première et le voipMobile (forwarder) et le deuxième soft-phone (receiver)
4. l'utilisateur fair le login par l'id et donna la permission pour voipMobile de transférer les appels entrants. (le telephone doit toujours connecté a l'internet)
5. l'utilisateur fair le login par l'id pour utiliser le soft-phone sur un autre telephone.

Le System est ready...


# Les different fonction du backend : 
| fonction   |      objectif      |  sous-fonction |
|----------|:-------------:|------:|
| Authentication |  utilisation de mots de passe sur des systèmes à temps partagé, pour l'authentification sécurisée de l'identité des clients du réseau par les serveurs et vice versa, sans présumer l'intégrité du système d'exploitation ni | genere, validee les jeton |
| SIP gateway |    le middleware entre les microservice et le SIP Server   |   convertir les SIP packet vers le RabbitMQ et vice versa|
| Payment gateway | faire le payment |    check balance, withdraw |
| Email notification | faire des notification via email |    check email, send email |
| SMS notification | faire des notification via SMS |    check MSISDN, send SMS |
| Notification orchestrator| faire le coordination entre les different notification |    Notification Routing  |
| Management | faire le management de system |    CRUD Subscriber, Notify, Call Payment Function|