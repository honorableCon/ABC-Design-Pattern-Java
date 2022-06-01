# Adapter

## Définition
L'adapteur est un patron structurel qui permet aux classes de travailler ensemble, ce qui ne pourrait pas être le cas autrement en raison d'interfaces incompatibles.
Il fonctionne comme un pont entre deux interfaces incompatibles.

## Cas d'utilisation

> Quand on veut adapter l’interface d’une classe pour qu’elle corresponde à l’interface attendue par un [client](/README.md#client)

## Implémentation

```java
interface IProjector {
    void acceptHDMI();
}

class Machine {
    public void acceptVGA() {
        System.out.println("Machine accept VGA");
    }
}

class Adapter implements IProjector {
    private Machine machine;

    public Adapter(Machine machine) {
        this.machine = machine;
    }

    @Override
    public void acceptHDMI() {
        machine.acceptVGA();
    }
}

class Client {
    public static void main(String[] args) {
        IProjector projector = new Adapter(new Machine());
        projector.acceptHDMI();
    }
}

```