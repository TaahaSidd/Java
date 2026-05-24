# Part - 7 - Polymorphism

**Polymorphism** :

1. It is one of the core concepts in OOPs.
2. It allows object to behave differently based on their specific class type.
3. The word polymorphism means having many forms, and it comes from Greek where poly (many) and morph(forms).
4. This means one entity can take many forms.
5. Multiple Behaviors : The same method can behave differently depending on the object that calls this method
6. Method Overriding : A child class can redefine a method of its parent class.
7. Method Overloading : We can define multiple methods with same name but different parameters.
8. Runtime decision : At runtime , Java determines which method to call depending on the object's actual class.

```
class Person{
    
    void Role(){
        Sop("I am Person");
    }
}

class Father extends Person{
    
    @Override
    void role(){
        Sop("I am Father");
    }
}

public class main{
    public static void main(String[] args){
        //Creating a reference of type person
        //but initializing it with father class object
        Person p = new Father();

        //Calling the role method. It calls the overridden version in  Father class.
        p.role();
    }
}

O/P -> I am Father - The person class has a method role() that prints a general message. The father class overrides role() to print a specific message. The reference of type person is used to point to an object of type father , demonstrating runtime polymorphism.
```