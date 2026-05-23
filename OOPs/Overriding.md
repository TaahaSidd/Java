# Part - 5 - Overriding

**Overriding** :

1. It allows a subclass to provide a specific implementation of method that is already defined in its parent class.
2. One of the key feature of runtime polymorphism in OOPs.
3. It is achieved when child and parent classes have methods with same signature.
4. Static, final and private methods cannot be overridden.
```
class Animal{
    void move(){
        Sop("Moving");
    }

    void Eat(){
        Sop("Eating");
    }
}

class Dog extends Animal{
    @Override void move(){
        Sop("Dog is moving");
    }
    
    @Override void eat(){
        Sop("Dog is eating");
    }
}
```
**Rules for Method overriding** :

1. Name, parameters and return type must match the parent method.
2. Java picks which method to run at runtime, based on the actual object type, not just the reference variable type.
3. Static methods cannot be overridden.
4. ```@Override``` annotation catches mistakes like typos in method names.
5. Covariant return type concept available only for objects types but not for primitive types.

**Special Cases for Overriding** :

1. Calling parent method using super - The super keyword can invoke the parent class method from the overriding method.

```
class Parent{
    void show(){

    }
}

child Child extends Parent{
    
    @Override
    void show(){
        super.show();
    }
}
```

2. Final methods cannot be overridden - If we don't want a method to be overridden, we declare it as final.

```
class Parent{
    
    final void show(){

    }
}

class Child extends Parent{
    void show(); -> We will get compile time error - overridden method is final
}
```

3. Static methods :
    1. Static methods cannot be overridden, defining a static method in a subclass with the same signature as in the superclass hides the superclass method.
    2. Instance method can be overridden, but a subclass cannot be override a superclass static method.
    3. A static method in subclass with the same signature as superclass static method hides the original method.
    
    ```
    class Parent{
        
        static void staticMethod(){
            Sop("Parent static method");
        }

        void instanceMethod(){
            Sop("Parent instance method");
        }
    }

    class Child extends Parent(){
        
        static void staticMethod(){ -> Hides parent's static method.
            Sop("Child Static method");
        }

        @Override
        void instanceMethod(){ -> Overrides Parent's instance method.
            Sop("Child instance method");
        }
    }
    ```

4. Private Methods :
    1. Private methods cannot be overridden because they are not visible to subclass.
    2. A subclass method with the same name is treated as new, independent method unrelated to the parent class.
    ```
    class Parent{
        
        private void display(){
            Sop("Parent private method");
        }
    }

    class Child extends Parent(){
        
        void display(){ -> This is a new method, not overriding.
            Sop("Child Method");
        }
    }
    ```

5. Covariant Return types :
   1. In method overriding, the return type of overriding method can be a subclass of the return type of the overridden method.
   2. This feature is known as covariant return type and allows specific return types in the subclass.
   ```
   class Parent{

        Parent getObject(){
            Sop("Parent Object");
            return new Parent();
        }
   }

   class Child extends Parent{
        
        @Override
        child getObject(){ -> Covariant return type.
            Sop("Child Object");
            return new Child();
        }
   }
   ```


**Method Hiding** :

1. If a subclass is defines a static method with the same signature as a static method in the superclass, then the method in the subclass hides the one in superclass.
2. This mechanism happens because the static method is resolved at the compile time.
3. Static method bind during the compile time using the type of reference not a type of object.

**Differences B/W Method Overriding and Method hiding** :

1. In method overriding both the method parent class and child class are non-static.
2. In method hiding both the method parent class and child class are static.
3. In method overriding method resolution is done on the basis of the Object type.
4. In method hiding method resolution is done on the basis of the reference type.
5. The version of the overridden instance method that gets invoked is the one in the subclass.
6. The version of the hidden static method that gets invoked depends on whether its invoked from the superclass or the subclass.
7. In method overriding, we have the ability to use the "super" keyword to explicitly access superclass methods (super keyword is non-static reference variable we cant use it in static method as we know static methods can only access static members of the class ). Therefore, method overriding does not involve method hiding since the "super" keyword allows us to access and invoke superclass methods when needed.