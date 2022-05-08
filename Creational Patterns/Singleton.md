# Singleton

## Définition

Le singleton est un model de conception qui permet de créer un objet unique qui sera accessible partout dans le programme.

## Cas d'utilisation

> Création d'instance de connexion à la base de données

## Implémentation

```java
public class Database {
    private static Database instance = null;
    
    private Database() {
        // initialisation de la connexion à la base de données
    }
    
    public static Database getInstance() {
        if (instance == null) {
            instance = new Database();
        }
        return instance;
    }
}
```
