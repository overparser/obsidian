>**Подтипы должны дополнять базовые типы.**
>
Если это разъяснить, то получится, что подклассы должны переопределять методы базового класса так, чтобы не нарушалась функциональность с точки зрения клиента. Подробно это можно рассмотреть на простом примере:

```
class Vehicle {
 
    function startEngine() {
        // Default engine start functionality
    }
 
    function accelerate() {
        // Default acceleration functionality
    }
}
```
>Есть существующий класс Vehicle, который может быть и абстрактным в том числе, и две реализации:

```
class Car extends Vehicle {
 
    function startEngine() {
        $this->engageIgnition();
        parent::startEngine();
    }
 
    private function engageIgnition() {
        // Ignition procedure
    }
 
}
 
class ElectricBus extends Vehicle {
 
    function accelerate() {
        $this->increaseVoltage();
        $this->connectIndividualEngines();
    }
 
    private function increaseVoltage() {
        // Electric logic
    }
 
    private function connectIndividualEngines() {
        // Connection logic
    }
 
}
```

>Клиентский класс должен иметь возможность использовать любой из них, если он может использовать Vehicle.

```
class Driver {
    function go(Vehicle $v) {
        $v->startEngine();
        $v->accelerate();
    }
}
```

[[S.O.L.I.D]] [[Liskov Substitution Principle]]