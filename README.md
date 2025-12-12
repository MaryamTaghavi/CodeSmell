# CodeSmell

** What are CodeSmells ?
CodeSmells create complexicity , duplicated code , unreadable code.
Some examples : 
* Duplicate Code => Seeing the exact code over and over again.
* Long Methods => We can broken logic into smaller methods, and one method must have single responsibility.
* Complex Conditional Statements => 

## Bloaters

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


