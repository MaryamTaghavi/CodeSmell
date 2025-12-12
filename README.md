# CodeSmell

** What are CodeSmells ?
CodeSmells create complexicity , duplicated code , unreadable code.
Some examples : 
* Duplicate Code => Seeing the exact code over and over again.
* Long Methods => We can broken logic into smaller methods, and one method must have single responsibility.
* Complex Conditional Statements => 

## Bloaters

1) LongMethod

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



