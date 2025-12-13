# Clean Code
In simple terms, Clean Code refers to code that is easy to read and understand—not only for the original developer, but also for teammates and future developers who will work on the same project. When code is written cleanly, the following benefits are achieved:

**Fewer defects:**

Clean and readable code allows issues to be identified more quickly. When code is complex and poorly structured, even the original author may struggle to locate bugs.

**Faster and safer development:**

Well-organized and structured code makes future changes and enhancements significantly easier. Without clean code, even minor modifications can negatively impact the entire system.

**Reduced time for comprehension:**

Clean code enables developers who are new to a project to understand its behavior and structure in a short amount of time. This results in faster onboarding and improved team productivity.

**Easier maintenance:**

Over time, maintaining and extending clean code becomes far simpler. Developers can continue the project with greater confidence, leading to a more stable and sustainable codebase.

**Professional satisfaction:**

Writing clean and well-crafted code provides a sense of professional fulfillment. Such code is easier to reuse, modify, and extend, even long after it was originally written.

# CodeSmell

** What are CodeSmells ?
CodeSmells create complexicity , duplicated code , unreadable code.
Some examples : 
* Duplicate Code => Seeing the exact code over and over again.
* Long Methods => We can broken logic into smaller methods, and one method must have single responsibility.
* Complex Conditional Statements => We can use interface for polymorphism.
* Tight coupling between classes
* Duplicate logic

** Why Code Smells Are Risky?
Ignoring Code Smells can lead to:
* Small changes causing big problems
* Slower code comprehension
* Bugs being discovered later than expected
* Team members being afraid to modify the code

## Bloaters
   - Bloaters are code, methods and classes that have increased to such gargantuan proportions that they’re hard to work with.
   
     I) LongMethods  II) Largeclass  III) PrimitiveObsession  IV) LongParameterList  V) DataClumps

1) Long Method

** Signs :
   - A method contains too many lines of code. Generally, any method longer than ten lines should make you start asking questions.
   - It’s easier to write code than to read it.
   - You feel the need to comment on something inside a method.

  <img width="681" height="340" alt="image" src="https://github.com/user-attachments/assets/7eeb165c-8df0-4ba1-aad4-82b1c58f094e" />


** Solutions :
   - To reduce the length of a method body, use Extract Method.
  <img width="952" height="245" alt="image" src="https://github.com/user-attachments/assets/bf3aa28f-ea04-46c1-bcee-e526d52031f9" />

   - Replace Temp with Query, Introduce Parameter Object or Preserve Whole Object.
  <img width="1176" height="393" alt="image" src="https://github.com/user-attachments/assets/48e1bdb0-3385-431b-b509-d6be8be62efc" />

   - You have a complex conditional (if-then/else or switch).
  <img width="1045" height="239" alt="image" src="https://github.com/user-attachments/assets/78b10a56-39e5-493e-871b-871a4fbc7386" />

2) Large Class

** Signs :
   - A class contains many fields/methods/lines of code.
   - Programmers usually find it mentally less taxing to place a new feature in an existing class than to create a new class for the feature.

** Solutions :
   - Extract Interface : Multiple clients use the samepart of code in different classes, so use interface for them.

3) Primitive Obsession

** Signs : 
   - Use of primitives instead of small objects or small classes.
   <img width="842" height="209" alt="image" src="https://github.com/user-attachments/assets/1889e3c3-9f4c-444b-a274-7f89afeb1a72" />

4) Long Parameter List

** Signs :
   - More than three or four parameters for a method.

** Solutions :
   - Preserve Whole Object : You get several values from an object and then pass them as parameters to a method. Instead, try passing the whole object.
   <img width="1263" height="184" alt="image" src="https://github.com/user-attachments/assets/6cdfb718-a064-4e39-bc64-d9f4101d433e" />

5) Data Clumps

** Signs :
   - Sometimes different parts of the code contain identical groups of variables, that can become a class.
   <img width="791" height="377" alt="image" src="https://github.com/user-attachments/assets/d69dd4c1-123d-4d93-b3ea-ba05e9135cae" />

## Object-Orientation Abusers
   - All these smells are incomplete or incorrect application of object-oriented programming principles.

   I) Switch Statements II) Refused Bequest

I) Switch Statements II) Couplers

** Signs :
   - You have a complex switch operator or sequence of if statements.

<img width="564" height="470" alt="image" src="https://github.com/user-attachments/assets/6506ba10-44fa-465c-b8e0-9e2d77bc0e52" />

** Solutions :
   - Use polymorphism

<img width="582" height="690" alt="image" src="https://github.com/user-attachments/assets/0274fed8-78bd-4ef1-8e0d-6fb14d5257f4" />

2) Refused Bequest

** Signs : 
   - If a subclass uses only some of the methods and properties inherited from its parents.

** Solutions :
   - Subclass need just one method of superclass / Create a field and put a superclass object in it, delegate methods to the superclass object, and get rid of inheritance.
   
     <img width="352" height="333" alt="image" src="https://github.com/user-attachments/assets/edad01d3-c2e3-492f-b1a8-8d9719e201e0" />
     <img width="417" height="263" alt="image" src="https://github.com/user-attachments/assets/ecdb60f1-1aa6-4809-9abe-685f0b1c662d" />


## Couplers
   - All the smells in this group contribute to excessive coupling between classes.

1) Feature Envy

** Signs :
   - A method accesses the data of another object more than its own data.
   - This smell may occur after fields are moved to a data class. If this is the case, you may want to move the operations on data to this class as well.
   - Decrease cohesion and increase coupling.

** Solutions :
   - Data and logic change together must be in a same class.
   - A method is used more in another class than in its own class, you must move that.

2) Message Chains

** Signs :
   - A method for getting data, must get data from B method and B must get data from c , ...
     In code you see a series of calls resembling $a->b()->c()->d()

** Solutions :
  - Instead of that "client.Order.Customer.Address.ZipCode" => "client.Order.GetCustomerZipCode()"

3) Middle Man

** Signs :
   - If a class performs only one action, delegating work to another class, why does it exist at all?
   <img width="584" height="407" alt="image" src="https://github.com/user-attachments/assets/5c957202-6b6d-4d28-8592-2c727a89cd51" />





