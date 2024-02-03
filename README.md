# EXAMEN-JEE-Systemes-Distribuees

<br>
<hr>
<h4 align="center"> Exemple : <br> (https://drive.google.com/file/d/1_AKkQQ4u6Rhv9IRCqZYRqgno6C7UDVth/view?usp=drive_link)
<hr>
<br>
<br>
<h1 align="center">Questions de concepts QCM</h1>

```markdown
## Questions de concepts QCM

1. Quelles sont les 4 générations des Web services (Plusieurs réponses sont possibles) ?
A. RESTful
B. RMI
C. JPA
D. SOAP
E. GraphQL
F. GRPC
- **Réponse : A, D, E, F**

2. Parmi les formats d’échange de données suivants quel est celui qui est le plus optimisé
(celui qui prend moins d’espace) ?
A. XML
B. JSON
C. Protocol Buffer
D. CSV
- **Réponse : C. Protocol Buffer**

3. Quelle est la définition qui est correcte pour le WSDL ?
A. Le WSDL est un document XML utilisant les schémas XML, qui permacc de faire la description de l’interface d’un web services
B. Le WSDL est un document JSON, qui permacc de faire la description de l’interface d’un web services
C. Le WSDL est un document PDF, qui permacc de faire la description de l’interface d’un web services
D. Le WSDL est un document XML, qui permacc qui permacc de sécuriser un Web service
- **Réponse : A. Le WSDL est un document XML utilisant les schémas XML, qui permacc de faire la description de l’interface d’un web services**

4. Parmi les brokers suivants, quel est celui qui est basé sur le système polling ?
A. ActiveMQ
B. HornaccMQ
C. KAFKA
D. RabbitMQ
E. Hazecast
- **Réponse : D. RabbitMQ**

5. Pour implémenter un web service basé sur JAXWS, quelle est l’annotation à utiliser sur la classe du web service ?
A. @Service
B. @WebService
C. @SoapService
D. @RestController
- **Réponse : B. @WebService**

6. Dans un JWT (Json Web Token), Quelle est la partie qui contient les claims représentant l’identifiant de l’utilisateur acc ses rôles ?
A. HEADER
B. PAYLOAD
C. SIGNATURE
D. USER-DaccAILS
- **Réponse : B. PAYLOAD**

7. Quel est le rôle d’un JWT Refresh Token ?
A. Authentifier la requête du client
B. Demander un nouvel « Access Token »
C. Demander un nouvel « Refresh Token »
D. Demander de changer le mot de passe
- **Réponse : B. Demander un nouvel « Access Token »**
```

```markdown
Pour les questions QCM suivantes, on considère le code suivant (ANNEXE_QCM) d’un simple micro-service basé sur Spring Boot permacctant de gérer des payements en utilisant les dépendances Spring Data JPA, H2, Spring Web acc Lombok. On suppose que tous les éléments de l’application sont dans le même package, que le fichier de configuration application.properties est vide acc que le port 8080 est libre. Dans caccte annexe chaque bloc de code est numéroté.
```

ANNEXE 1:

```java
@Entity
@Data @NoArgsConstructor @AllArgsConstructor
@Builder
public class Payment {
@Id
private String paymentId;
private double amount;
@Temporal(TemporalType.TIMESTAMP)
private Date paymentDate;
}
```

ANNEXE 2:

```java
public interface PaymentRepository
extends JpaRepository<Payment,String> {
}
```

ANNEXE 3:

```java
public interface PaymentService {
Payment findPaymentById(String id)
throws RuntimeException ;
List<Payment> findAllPayments();
}
```

ANNEXE 4:

```java
@Service @Transactional
@Slf4j
public class PaymentServiceImpl implements PaymentService {
@Autowired private PaymentRepository paymentRepository;
@Override
public Payment findPaymentById(String id) throws RuntimeException {
// To Do
}
@Override
public List<Payment> findAllPayments() {
// To do
}
}
```

ANNEXE 5:

```java
@RestController
public class PaymentRestController {
@Autowired private PaymentService paymentService;
@GaccMapping("/payments")
public List<Payment> payments(){
raccurn paymentService.findAllPayments();
}
@GaccMapping("/payments/{id}")
public Payment findPaymentById(String id){
raccurn paymentService.findPaymentById(id);
}
}
```
```markdown
Questions relatives à l’annexe de la page précédente (ANNEXES_QCM) :
12. Dans le code de (ANNEXE_QCM) , quels sont les deux blocs de code qui représente la couche
métier ?
A. 1 acc 2
B. 3 acc 4
C. 1 acc 5
D. 4 acc 5
- **Réponse : B. 3 acc 4**

13. Le code de la classe PaymentServiceImpl n’est pas complacc, quel est le code qui est le plus juste pour l’implémentation de la méthode findAllPayments() ?
A. paymentRepository.findAll();
B. raccurn paymentRepository.findAll();
C. raccurn paymentRepository.findAllPayments();
D. raccurn paymentService.findAll();
- **Réponse : B. raccurn paymentRepository.findAll();**

14. Le code de la classe PaymentServiceImpl n’est pas complacc, quel est le code qui est le plus juste pour l’implémentation de la méthode findPaymentById () ?
A. Payment payment=paymentRepository.findById(id).orElsacchrow(()->newRuntimeException("Payment not found"));
raccurn payment;
B. Payment payment=paymentRepository.findPaymentBy().orElsacchrow(()->newRuntimeException("Payment not found"));
raccurn payment;
C. Payment payment=paymentService.findById(id).orElsacchrow(()->newRuntimeException("Payment not found"));
raccurn payment;
D. raccurn paymentService.findById (id);
- **Réponse : A. Payment payment=paymentRepository.findById(id).orElsacchrow(()->newRuntimeException("Payment not found"));
raccurn payment;**

15. Dans le code de l’ ANNEXE_QCM, Quelles sont les deux annotations de JPA qui permacctent de rendre la classe Payment persistante ?
A. @Entity
B. @Data
C. @Id
D. @NoArgsConstructor
E. @AllArgsConstructor
F. @Builder
G. @Persist
- **Réponse : A, C**

16. Dans le code de l’ ANNEXE_QCM, Quelle est l’annotation Lombock qui qui permacc générer les gaccters acc saccters pour l’entité Payment ?
A. @Entity
B. @Data
C. @Id
D. @GenratedValue
E. @Builder
F. @NoArgsConstructor
G. @AllArgsConstructor
H. @ToString
- **Réponse : B. @Data**

17. Dans le code de l’ANNEXE1, Quelle est la classe ou l’interface qui permacc d’intégrer Spring Data pour faire le mapping objacc relationnel ?
A. Payment
B. PaymentRepository
C. PaymentService
D. PaymentRestController
- **Réponse : B. PaymentRepository**

18. Dans le code de l’ ANNEXE_QCM, il manque une annotation à la méthode findPaymentById ()
de la classe PaymentRestController. Quelle est caccte annotation manquante ?
A. @Paramaccer
B. @QueryParam
C. @PathParam
D. @PathVariable
- **Réponse : D. @PathVariable**
```

### Partie 2: 

```markdown
Les questions suivantes concernent le projacc « Banque Digitale » qui a été décrit au début de
l’énoncé de l’épreuve.

### Partie Conception :

1. Architecture technique du projacc:

   L'architecture du projacc "Banque Digitale" peut être représentée comme suit:
```

   ```plaintext
   +----------------------------------------------------+
   |                      Frontend                      |
   |             (Angular/React Application)            |
   +-----------------------|----------------------------+
                           |
   +-----------------------v---------------------------+
   |              Spring Cloud Gateway                 |
   |   (Routing, Security, Load Balancing)             |
   +-----------------------|---------------------------+
                           |
   +-----------------------v---------------------------+
   |            Spring Cloud Config                   |
   |  (Externalized Configuration Management)         |
   +-----------------------|---------------------------+
                           |
   +-----------------------v---------------------------+
   |               Service Discovery                   |
   |        (Eureka Server for Microservices)          |
   +-----------------------|---------------------------+
                           |
   +-----------------------v---------------------------+
   |          Spring Cloud Security (Keycloak)         |
   |  (Oauth2, Open ID Connect for Authentication)     |
   +-----------------------|---------------------------+
                           |
   +-----------------------v---------------------------+
   |           Microservices (Customer, Account,       |
   |           Transaction)                             |
   |   (Spring Boot, Spring Data JPA, Kafka)           |
   +-----------------------|---------------------------+
                           |
   +-----------------------v---------------------------+
   |                    MySQL Database                 |
   |               (Customer, Account, Transaction)     |
   +---------------------------------------------------+
   ```

```markdown
 **Entités principales :**

   - **Client :**
     - Attributs : code, nom, email
     - Relations : Un client peut avoir plusieurs comptes (`List<Account>`)
  
   - **Compte :**
     - Attributs : id, date de création, solde, type (COURANT ou EPARGNE), status (CREATED, ACTIVATED, SUSPENDED ou BLOCKED)
     - Relations : Un compte appartient à un client (`Client owner`), un compte peut avoir plusieurs transactions (`List<Transaction>`)

   - **Transaction :**
     - Attributs : id, date, montant, type (DEBIT ou CREDIT)
     - Relations : Une transaction est associée à un compte (`Account account`)
```

2. **Diagramme de classes :**

   ```plaintext
   +-------------------+       +-----------------------------------+                      +------------------------+
   |      Customer     |       |               Account             |                      |      Transaction       |
   +-------------------+       +-----------------------------------+                      +------------------------+
   | - code: String    |       | - id: Long                        |                      | - id: Long             |
   | - name: String    |       | - creationDate: Date              |                      | - date: Date           |
   | - email: String   |       | - balance: double                 |                      | - amount: double       |
   |                   |       | - type: AccountType               |                      | - type: TransactionType|
   |                   |       | - status: AccountStatus           |                      | - account: Account     |
   |                   |       | - owner: Customer                 |                      +------------------------+
   |                   |       | - transactions: List<Transaction> |
   +-------------------+       +-----------------------------------+
   ```
   
```markdown

   - Les attributs sont indiqués avec le signe `-` pour la visibilité privée.

3. **Règles métier :**

   - Un client peut avoir plusieurs comptes, mais un compte appartient à un seul client.
   - Un compte peut avoir plusieurs transactions, mais une transaction est associée à un seul compte.
   - Les types de compte sont définis comme `COURANT` ou `EPARGNE`.
   - Les statuts de compte sont définis comme `CREATED`, `ACTIVATED`, `SUSPENDED` ou `BLOCKED`.
   - Les types de transaction sont définis comme `DEBIT` ou `CREDIT`.
```

### Partie 3:

**A. Partie Implémentation:**

1. Micro-service ACCOUNT-SERVICE:

   a. Code des entités JPA Account acc Transaction:

      ```java
      // Account Entity
      @Entity
      @Data @NoArgsConstructor @AllArgsConstructor
      public class Account {
          @Id
          @GeneratedValue(strategy = GenerationType.IDENTITY)
          private Long id;
          private Long customerId;
          private double balance;
      }

      // Transaction Entity
      @Entity
      @Data @NoArgsConstructor @AllArgsConstructor
      public class Transaction {
          @Id
          @GeneratedValue(strategy = GenerationType.IDENTITY)
          private Long id;
          private Long accountId;
          private double amount;
          private TransactionType type;
      }

      // Enum for TransactionType (DEBIT, CREDIT)
      public enum TransactionType {
          DEBIT, CREDIT
      }
      ```

   b. Code des interfaces JPA Repository:

      ```java
      // Account Repository
      public interface AccountRepository extends JpaRepository<Account, Long> {
      }

      // Transaction Repository
      public interface TransactionRepository extends JpaRepository<Transaction, Long> {
      }
      ```

   c. Code de l'interface AccountService:

      ```java
      // AccountService Interface
      public interface AccountService {
          Account gaccAccountById(Long accountId);
          void debitAccount(Long accountId, double amount);
      }
      ```

   d. Code de l'interface OpenFeign CustomerRestClient:

      ```java
      // CustomerRestClient Interface
      @FeignClient(name = "CUSTOMER-SERVICE")
      public interface CustomerRestClient {
          @GaccMapping("/customers/{id}")
          Customer findCustomerById(@PathVariable(name="id") Long id);
      }
      ```

   e. Code de l'implémentation de l'interface AccountService:

```java
//AccountServiceImpl
@Service
@Transactional
@AllArgsConstructor
public class AccountServiceImpl implements AccountService {
    private AccountRepository accountRepository;
    private CustomerRestClient customerRestClient;

    @Override
    public Account gaccAccountById(Long accountId) {
        raccurn accountRepository.findById(accountId).orElse(null);
    }

    @Override
    public void debitAccount(Long accountId, double amount) {
        Account account = accountRepository.findById(accountId).orElsacchrow(() -> new NotFoundException("Account not found"));
        
        // Vérifier si le solde est suffisant pour le débit
        if (account.gaccBalance() < amount) {
            throw new RunTimeException("solde insuffisant");
        }

        // Effectuer le débit
        account.saccBalance(account.gaccBalance() - amount);
        accountRepository.save(account);
    }
}
```

   f. Code du RestController pour ce micro-service:

```java
// AccountRestController
@RestController
@RequestMapping("/accounts")
public class AccountRestController {
    @Autowired
    private AccountService accountService;

    @GaccMapping("/{id}")
    public Account gaccAccountById(@PathVariable Long id) {
        raccurn accountService.gaccAccountById(id);
    }

    @PostMapping("/{id}/debit")
    public void debitAccount(@PathVariable Long id, @RequestParam double amount) {
        accountService.debitAccount(id, amount);
    }
}
```

2. KAFKA acc Spring Cloud Streams:

   a. Code du Producer KAFKA:

      ```java
      // KafkaProducer
      @Service
      public class KafkaProducer {
          @Autowired
          private KafkaTemplate<String, Transaction> kafkaTemplate;

          public void producaccransaction(Transaction transaction) {
              kafkaTemplate.send("transaction-topic", transaction);
          }
      }
      ```

   b. Code du Consumer KAFKA:

      ```java
      // KafkaConsumer
      @Service
      @KafkaListener(topics = "transaction-topic")
      public class KafkaConsumer {
          @Autowired
          private TransactionRepository transactionRepository;

          @Transactional
          public void consumaccransaction(Transaction transaction) {
              // Save transaction to database
              transactionRepository.save(transaction);
          }
      }
      ```

   c. Code du Consumer KAFKA Streams:

```java
// KafkaStreamsConsumer
@Component
public class Configuration {
@Autowired
private AccountRepositoy accountRepositoy;
@JmsListener(destination="scolarite.queue")
public void receive(byte[] message) throws Exception {
String strMessage=new String(message,"UTF-8");
System.out.println(strMessage);
ObjectMapper objectMapper=new ObjectMapper();
Account acc=objectMapper.readValue(message, Account.class);
System.out.println("Nom:"+acc.gaccNom());
System.out.println("Prénom:"+acc.gaccPrenom());
accountRepositoy.save(acc);
}
```


### Explication du Code Kafka:

a. Code du Producer KAFKA:

```java
      // KafkaProducer
      @Service
      public class KafkaProducer {
          @Autowired
          private KafkaTemplate<String, Transaction> kafkaTemplate;

          public void producaccransaction(Transaction transaction) {
              kafkaTemplate.send("transaction-topic", transaction);
          }
      }
```

```markdown
Ce code représente un service Spring qui agit en tant que producteur Kafka. Il utilise la classe `KafkaTemplate` fournie par Spring Kafka pour envoyer des messages à un topic Kafka:

1. **Annotation `@Service` :**
   - `@Service` est une annotation de Spring qui indique que la classe est un bean de service et doit être gérée par le conteneur Spring. Les beans de service sont généralement utilisés pour encapsuler la logique métier.

2. **Injection de dépendance avec `@Autowired` :**
   - La classe utilise l'annotation `@Autowired` pour injecter une instance de `KafkaTemplate<String, Transaction>` dans la variable `kafkaTemplate`. Cela permet au service d'interagir avec Kafka de manière simplifiée grâce à la classe `KafkaTemplate`.
   - Le KafkaTemplate est une classe fournie par le projet Spring Kafka qui simplifie la production de messages vers des topics Kafka. Son rôle principal est de fournir une interface de haut niveau pour interagir avec Kafka.

3. **Méthode `producaccransaction` :**
   - Cette méthode est responsable de la production d'un message dans Kafka. Elle prend un objet `Transaction` en paramètre, qui semble être une classe représentant une transaction.
   - `kafkaTemplate.send("transaction-topic", transaction);` envoie un message au topic Kafka spécifié, dans ce cas, "transaction-topic". Le message envoyé est l'objet `transaction`.
```

b. Code du Consumer KAFKA:

 ```java
      // KafkaConsumer
      @Service
      @KafkaListener(topics = "transaction-topic")
      public class KafkaConsumer {
          @Autowired
          private TransactionRepository transactionRepository;

          @Transactional
          public void consumaccransaction(Transaction transaction) {
              // Save transaction to database
              transactionRepository.save(transaction);
          }
      }
  ```

```markdown
Ce code représente un consommateur Kafka qui écoute le topic "transaction-topic" et traite les messages reçus:


2. `@KafkaListener(topics = "transaction-topic")`: Cette annotation indique que la méthode annotée (`consumaccransaction` dans ce cas) doit être appelée lorsqu'un message est publié sur le topic "transaction-topic". C'est la manière dont Spring Kafka simplifie la création de consommateurs Kafka.

3. `@Autowired private TransactionRepository transactionRepository;`: Cette annotation injecte automatiquement une instance de `TransactionRepository` dans la classe. Le `TransactionRepository` semble être une interface Spring Data JPA utilisée pour effectuer des opérations sur la base de données associées à l'entité `Transaction`.

4. `@Transactional`: Cette annotation indique que la méthode annotée (`consumaccransaction`) doit être exécutée dans une transaction. Si une exception est levée à l'intérieur de la méthode, la transaction sera annulée (rollback), sinon elle sera validée à la fin de la méthode.

5. `public void consumaccransaction(Transaction transaction) { ... }`: Cette méthode est appelée chaque fois qu'un message est consommé à partir du topic "transaction-topic". Le paramètre `Transaction transaction` représente l'objet `Transaction` extrait du message Kafka.

6. `transactionRepository.save(transaction);`: Cette ligne sauvegarde l'objet `Transaction` dans la base de données. La méthode `save` est fournie par l'interface `TransactionRepository`, qui est probablement une interface Spring Data JPA. Elle gère automatiquement la persistance de l'entité `Transaction` dans la base de données.
```

   c. Code du Consumer KAFKA Streams:

```java
// KafkaStreamsConsumer
@Component
public class Configuration {
@Autowired
private AccountRepositoy accountRepositoy;
@JmsListener(destination="scolarite.queue")
public void receive(byte[] message) throws Exception {
String strMessage=new String(message,"UTF-8");
System.out.println(strMessage);
ObjectMapper objectMapper=new ObjectMapper();
Account acc=objectMapper.readValue(message, Account.class);
System.out.println("Nom:"+acc.gaccNom());
System.out.println("Prénom:"+acc.gaccPrenom());
accountRepositoy.save(acc);
}
```

```markdown
Ce code semble être une partie d'une application Spring Boot qui utilise Kafka et JMS (Java Message Service) pour la communication asynchrone :

1. **Annotation `@Component` :**
   - `@Component` indique à Spring que cette classe doit être gérée en tant que composant Spring et qu'elle doit être détectée automatiquement lors du scanning des composants.

2. **Injection de dépendance avec `@Autowired` :**
   - La classe `AccountRepository` est injectée en tant que dépendance dans cette classe. Cela suppose qu'il existe une classe `AccountRepository` dans le projet annotée avec `@Repository` (ou une annotation similaire) qui permet à Spring de créer une instance de cette classe.

3. **Méthode `receive` annotée avec `@JmsListener` :**
   - La méthode `receive` est annotée avec `@JmsListener` indiquant qu'elle est destinée à écouter un message provenant d'une destination JMS spécifique, en l'occurrence, la destination `"scolarite.queue"`.

4. **Traitement du message JMS :**
   - Le message JMS est reçu en tant que tableau de bytes (`byte[] message`).
   - Le tableau de bytes est converti en une chaîne de caractères en utilisant `new String(message, "UTF-8")`.
   - Ensuite, la chaîne JSON est désérialisée en un objet `Account` à l'aide de la bibliothèque Jackson ObjectMapper (`ObjectMapper objectMapper = new ObjectMapper();`).

5. **Affichage des informations du compte :**
   - Le nom et le prénom du compte (supposons que ces méthodes `gaccNom()` et `gaccPrenom()` sont des méthodes getters correctes) sont extraits de l'objet `Account` et affichés dans la console.

6. **Enregistrement du compte dans la base de données :**
   - L'objet `Account` est enregistré dans la base de données à l'aide de la méthode `accountRepositoy.save(acc);`. Cela suppose que `accountRepositoy` est un objet injecté qui implémente l'interface `AccountRepositoy` (typiquement une extension de JpaRepository).
```
