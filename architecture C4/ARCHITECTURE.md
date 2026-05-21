# Architecture C4 Model - Plateforme E-learning

## Niveau 1 : Diagramme de Contexte

```mermaid
C4Context
    title Diagramme de Contexte - Plateforme E-learning
    
    Person(apprenant, "Apprenant", "Étudiant qui suit des cours")
    Person(instructeur, "Instructeur", "Crée et gère des cours")
    Person(admin, "Administrateur", "Supervise la plateforme")
    
    System(plateforme, "Plateforme E-learning", "Microservices + IA Tutor + n8n")
    
    System_Ext(paiement, "Passerelle de paiement", "Stripe/PayPal")
    
    Rel(apprenant, plateforme, "Suit des cours, pose des questions", "HTTPS")
    Rel(instructeur, plateforme, "Crée des cours, consulte les feedbacks", "HTTPS")
    Rel(admin, plateforme, "Supervise et modère", "HTTPS")
    Rel(plateforme, paiement, "Paiements cours payants", "API")