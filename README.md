# Fort
Fort is an application architecture on top of MVC. It mainly focuses on security & modularity.

Fort can be implemented in any language, frontend & backend.

## Fort avalaibles are 

### JavaScript 
* BackEnd - fortjs

If you are creating/created a framework - please fork this repo, update the readme. 

# Principle

In general - "fort is a strong building having wall, guards etc which is used to protect some resources". 

Fort architecture uses this definition, so your app becomes a fort and you have to focus on creating different components in order to make your app secure and modular.

## Inside fort 

* Controller is a section where a list of resources of particular types are available.
  
  e.g - A Fort may have sections - WeaponSection, LibrarySection, MeetingSection etc. 
* Methods inside a controller are actions. Not every method is actions , you might have a private or protected which you dont like to share with outside world.
* Actions are the end resources which a fort share with outside world.

## Components

Fort have three main componenents - 

* **Wall** - Wall is security layer on top of your app. It controls whether a request should be allowed to enter inside the app (Remeber your app is now a Fort :grimacing:). It can also be used to do some tasks and pass inside app. 
  
  e.g - Consider a situation where requests from a ip has over trafficked your app and you want to block it. Wall can be used in this situation.
* **Shield** - Shiled is security layer on top of **Controller**. It controls whether a request should be allowed to enter inside the Controller. It can also be used for doing some task before passing it to actions.
  
  e.g - Consider a case - where a controller "Admin" is only allowed if the request is authenticated. You can create a shield which will check for the authentication. And if it does not satisfy the conditions, you can just reject it. 
* **Guard** - Guard is security layer on top of **Action**. It contols whether a request should be allowed to enter inside the action.
  
  e.g - Consider some one comes into your fort , section weapons asking for a sword (already passed wall and shield). In order to identify the sword you have some questions - 1. Who sent you ? 2. What's sword identifier? and you want to be sure that they have valid answer. For this you keep a guard and told them - hey ask these questions and if they have valid answer then let them take the resources. 
