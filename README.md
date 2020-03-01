# Fort
Fort is an application architecture on top of MVC. It mainly focuses on security & modularity.

Fort can be implemented in any language, frontend & backend.

##  Avalaible Forts are 

* [fortjs](https://github.com/ujjwalguptaofficial/fortjs) - MVC web framework for nodejs targeting good code structures & modularity.
* [Shivneri](https://github.com/ujjwalguptaofficial/shivneri) - MVC web framework for crystal lang.

If you are creating/created a framework - please update the readme and send a PR. 

# Principle

In general - "fort is a strong building having wall, guards etc which is used to protect some resources". 

Fort architecture uses this definition, so your app becomes a fort and you have to focus on creating different components in order to make your app secure and modular.

## Inside fort 

* Controller is a section where a list of resources of particular types are available.
  
  e.g - A real fort may have sections - WeaponSection, LibrarySection, MeetingSection etc. 
* Methods inside a controller are called Workers. A worker does some particular task and return the final result. Not every method is worker - you might have a method which is being used by Worker. Methods which is being used by workers are like subordinate which helps them to complete a task.


## Components

Fort have three main componenents - 

* **Wall** - Wall is security layer on top of your Fort. It controls whether someone should be allowed to enter inside the fort (Remeber your app is now a Fort :grimacing:). It can also be used to do some tasks and pass the data along with request inside fort. 
  
  e.g - 
  * Consider a situation where visitors from a particular address is coming so many times (requests from a ip) and you want to restrict their acess to fort.
  * Another situation where your fort requires the address of every visitor, so you ask them what is your address and pass the address inside the fort. So when the visitor go to any section, the sections have already knowledge of the visitor address.
* **Shield** - Shiled is security layer on top of Section (Controller). It controls whether a request should be allowed to enter inside the Section. It can also be used for doing some task before passing it to sections.
  
  e.g - Consider a case - where a controller "Admin" is only allowed if the request is authenticated. You can create a shield which will check for the authentication. And if it does not satisfy the conditions, you can just reject it. 
* **Guard** - Guard is security layer on top of **Worker**. It contols whether a request should be allowed to access the worker.
  
  e.g - Consider some one comes into your fort , section weapons asking for a sword (already passed wall and shield). In order to identify the sword you have some questions - 
  1. Who sent you ? 
  2. What's sword identifier? 
   
   and you want to be sure that they have valid answer. For this you keep a guard and told them - hey ask these questions and if they have valid answer then let them take the resources. 

## Summary - 

* Fort is divided into sections. Section contains resources of particular type.
* Section has workers which does some work and return the final results.
* A wall is a top level component which can be used to block the visitor or do some task before allowing the visitor.
* A shield is a section level component which blocks the visitor for entering into sections or can be used as doing some task before allowing the visitor.
* A guard is a worker level component. They guard the workers and can also be used to do some task before passing the task to worker.
