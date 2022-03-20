# Property Decorator and Property Method
 - Property decorator (i.e `@property`) as well as Property method (i.e`property()`) provide same functionalty.

 - That is of to enable the user **to access a member method as member variable of a class**.

 - With variable, we can **Set** its value, **Get**(retrieve) its value and **Delete** its value.

 - Therefore when accessing a method as variable we want all these three functionalities (as mentioned above).

 - For each of these functionality we have to create separate methods.

 - Three functionality means three methods namely - **Getter**, **Setter**, and **Deleter**.

### CASE 1: Using Property Decorator 
 When using property deorator (i.e `@property`) all three method must have to follow an nameing convention that is,

 If `@property` decorator is applied to a method - let us say `fullname()` then, property decorators will be applied as follows:

 ```
 class Classname:
 
    # this method will serve as setter
    @property
    def fullname(self,):
        pass

    @fullname.getter
    def fullname(self,):
        pass

    @fullname.deleter
    def fullname(self,):
        pass
 ```
   ## OR
  ```
 class Classname:
 
    # this method will serve as getter
    @property
    def fullname(self,):
        pass

    @fullname.setter
    def fullname(self,):
        pass

    @fullname.deleter
    def fullname(self,):
        pass
 ```
   ## OR
 ```
 class Classname:
 
    # this method will serve as deleter
    @property
    def fullname(self,):
        pass

    @fullname.setter
    def fullname(self,):
        pass

    @fullname.getter
    def fullname(self,):
        pass
 ```
 **Convention is that, all the methods must have same name.**

### CASE 2: Using Property Method 
When using Property method (i.e `property()`) we can create **Getter**, **Getter** and **Deleter** method with any name. 

But **after creating all these three methods** we have to create a `property()` method object by passing name of Getter, Setter, and Deleter method in order.

For example:
```
class Classname:
    
    def anyname(self,):
        pass

    def funnyname(self,):
        pass

    def bunnyname(self,):
        pass

    varname = property(anyname, bunnyname, funnyname)
 ```
 Its not neccessay to have all three - Getter, Setter and Deleter method. If thats the case we have to pass method name as Keyword argument, that is,
 ```
 varname = property(fget=anyname, fset=bunnyname, fdel=funnyname)
 ```
 
 ### Complete Use case of Property decorator and property method
 ```
 class Student:
    """Usecase of property decorator and property method."""
    def __init__(self, fname, lname) -> None:
        self.fname = fname
        self.lname = lname
        #self.fullname = f"{fname} {lname}"

    #@property
    #def fullname(self):
    def get_fullname(self):
        return f"{self.fname} {self.lname}"

    #@fullname.setter
    #def fullname(self, name):
    def set_fullname(self, name):
        self.fname, self.lname = name.split()
    
    #@fullname.deleter
    #def fullname(self):
    def del_name(self):
        self.fname = None
        self.lname = None
    
    fullname = property(fget=get_fullname, fset=set_fullname, fdel=del_name) 

obj = Student("Omprakash", "Mishra")
print(obj.fullname)

obj.fname = "Pratham"
print(obj.fullname)

obj.fullname = "Nishant Tiwari"
print(obj.fname)
print(obj.lname)
print(obj.fullname)

del obj.fullname
print(obj.fullname)
```
**Output be like: **
```
Omprakash Mishra
Pratham Mishra
Nishant
Tiwari
Nishant Tiwari
None None
```
