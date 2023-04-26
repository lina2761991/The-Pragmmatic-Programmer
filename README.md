# The pragmatic Programmer

# chapter1. A pragmatic philosophy 
* Don't leave broken windows; whenever there's something broken fix it as soon as possible because that might be the beginning of the damage
* Stone soup story, start adding something then watch everyone gathering up around you and adding other things despite the " start-up fatigue"
* Always keep in mind the big picture  
* you have to know when to stop, no need to keep adding stuff, it might ruin your code
* pay attention to your knowledge portfolio, and take your learning seriously
*  invest in your knowledge portfolio( rules are page 15- 16 ) following these tips:
- diversification is key
- update portfolio periodically
* be a critical thinker ( ask why 5 times , it will often lead you to the real reason)
* communicate and care about feedback as much, as ways of communicating, timing and presentation are as important
*documenting is so important, always metion why smthg is done and its purpose

# chapter2. A pragmatic approach
## Dry
* good design make things easier to change (ETC) the decoupling principale
* maintenance is always beig done, main thing is dont repeat your self (DRY) method
* Try as much as possible to reduce the duplication and put things into functions to reuse them
* sometimes 2 functions have different names but they do the same thing ,but the knoweldge they represent is different, this is not duplication, this is a coincidence
* often developers duplicate the same thing in the same project without knowing, thats why u have to pay attention on the daily scrum meeting , read ur collegue code and documentation and reuse it if its useful for you , generally if a code is easy to read and is reusuable then its a good code 

## Orthogonality( decoupling)
* non orthogonal is like a helicopter system , too complicated , whenever you touch just one simple thing , smthg else gets affected , the whole system is so interconnected and complex , you cant focus on fixing just one thing without the other
* orthogonal systems, they are composed of elements that aren't inter-dependent on each other, the interfaces are linked but deep inside each element has its own structure, so if you wanna fix something you focus on just one thing, not the whole system
### Benefits of orthogonality:

        *  increase productivity and reduce risk
        * better to focus on small thing
        * re-usability
        * fix particular area, less spreading bad functionalities
        * you can do this tricky test to check your orthogonality; you say if I make a slight change in my system in a specific thing, how would this affect the entire thing 
        have the habit of refactoring 
        * orthogonality + Dry => flexible system

## Reversibility:
* Be prepared for changes. 
* Tip 14: There are no Final Decisions.
* flexible architecture 
* tracer code /tracer bullets
* In new projects your users requirements may be vague. Use of new algorithms, techniques, languages, or libraries unknowns will come. And environment will change over time before you are done. We're looking for something that gets us from a requirement to some aspect of the final system quickly, visibly, and repeatably.
* Tracer Bullets Don't Always Hit Their Target
* Tracer bullets show what you're hitting. This may not always be the target. You then adjust your aim until they're on target. That's the point.
* Tip 15: Use Tracer Bullets to Find the Target

Advantages of tracer bullets:


    • Users get to see something working early
    • Developers build a structure to work in
    • You have an integration platform
    • You have something to demonstrate
    • You have a better feel for progress

### Prototyping
* tracer code approach isn't the same as prototyping (target just one or 2 aspects of the project, not the whole thing
* post it notes and drawing the user interface on white board are types of prototyping) while tracer bullet style is when u care  about the details
* we use prototyping in these cases;
* architecture – new functionalities in an existing system – user interface design 
#### Details to ignore in prototyping :

* correctness – completeness – robustness – style  
* always remind whoever is seeing the prototype that this is not real, its just a prototype

* => if you feel the prototype might be misleading, you better use the tracer bullet approach

### Estimating
* What to Say When Asked for an Estimate
* "I'll get back to you."
* Scale time estimates properly

* Duration - Quote estimate in

* 1-15 days  -   days
* 3-8 weeks   -  weeks
* 8-30 weeks  -  months
* 30+ weeks  -  months

* think hard before giving an estimate
* notes
* Start keeping a log of your estimates. For each, track how accurate you turned out to be. If your error was greater than 50%, try to find out where your estimate went wrong.

#### Estimating Project Schedules
* The only way to determine the timetable for a project is by gaining experience on that same project. 
* Practice incremental development, repeating the following steps:
   
    • Guess estimation
    • Check requirements
    • Analyse risk
    • Design, implement, integrate
    • Validate with the users
    • Repeat


# chapter3. The basic tools
 ### The power of plain text
* knowing how to manipulate the shell is important cuz if u dont , u r missing out alot of things 
* u can personlize ur own shell
### fluent in editing ; 
* saves time between thinking and seing it appear   
###  version control; 
* it givezs us the ability to go back in time in version control system and go back to any time of the project 
* shared directory isnt vcs   (like putting the project on the cloud and everyone makes changes on it), every user needs to have his own version and update it (concept of branches)


# chapter4. Pragmatic paranoia

 #### DBC;
* design by contract; simply enumerating wht the input range is, wht the boundary conditions are, wht the routine promises to deliver and wht it doesnt promise to deliver( its so important to use this technique its the opposite of programming by coincidence)
* using assertions ;these are runtime checks
* DBC and assert r used to validate pre conditions, post conditions and invariants

#### Assertations 
* they check for things that should never happen
* dont turn off the assertation even in production , cuz even tests cant replace them even if u feel they make the program kinda heavy
* finish wht you start
* always like opening and closing a file ( practice decoupling as much as possible( #of coupling))
*act locally
* whoever allocate a ressource should be responsible for dellocating it
* basic ressource allocation pattern isnt appropriate when we have dynamic datastructures
* take small steps always 
#### When to Use Exceptions
* Tip 34: Use Exceptions for Exceptional Problems
* The program must run if all the exception handlers are removed If your code tries to open a file for reading and that file does not exist, should an exception be raised

    • Yes: If the file should have been there
    
    • No: If you have no idea whether the file should exist or not
    
    
# chapter5.Bend or Break

* write a flexible code that can be replaceable
* Decoupling
* coupling is the enemy of change
* we need flexible,easy to change code
* static things and inhritence are dangerous
* we shouldnt chain method calls  = > try to have no more than one “.” when u wanna access smthg 
* global data creates coupling (this Pb appears in unit testing)
* global data includes singleton and external ressources 
* => if its important enough to be global, wrap it in an api

#### Jiggling the real world  

* writing programs that are responsive to changes and needs 
## Events

* the 4 strategies that help with events ;

     1. finite state machine
     state machine is a sspecification how to handle events 
     2. the observer pattern
     theres an observer and observable 
     3. publish/subscribe
     solves the problem of coupling of the observer/observable
     4. reactive programming and streams
     
#### transforming programming

* some languages use pipelines like R %>% meaning the output of a line of code is the input of another
* other languages that use OOP tend to do the same by creating object variables, sometimes we can use the “.” to call a function inner function inner function but this is not recommanded and its called train wreck( the code is this case in so coupled and hard to modify or manipulate)
#### Inheritence Tax
* its not recomanded to use inheritence
* alternatives of inheritance are ; 

        * interfaces and protocols
        * delegation
        * mixings and traits
        * Configurations
        

* Things to include in the configuration file:

      * Credentials for external services (database, third party APIs, and so on) 
      * Logging levels and destinations Port, IP address, machine 
      * cluster names the app uses Environment-specific validation parameters
      * Externally set parameters, such as tax rates Site-specific formatting details 
      * License keys 
      
# chapter6.Concurrency

* concurrency is when pieces of code act like they run at the same time 
* parallelism is when pieces of code actually run at the same time
* concurrency is usually mentionned in the activity diagram
* during concurrency we look for activities that would take time so we can do other acitivities at same time
* concurrency is software mechanism while parallelisme is a hardware mechanism

# chapter7.while you are coding

* we have to trust our intuition while coding ( the lizard brain)
* avoid coding by coincidence , we have to understand why the code worked at first in order to be able to fix it later if smthg goes wrong

#### testing reduces coupling 
* unit testing is about testing each unit individually on each own 
* no matter how much we test the prod environment has its own magic of bringing out bugs
* we cant use debugger in production, we use log files that contain trace messages
* tests are not for someone experienced to use them, he got used to coding so he can predict them while coding without “typing them” but its a good way to communicate between developers
* we have unit tests and property based tests
* unit test is your first client of the api
* property based tests ;make u think of the code in terms of invariants and contracts

=> think abt wht we must not change and wht must be true 
both kinds of tests are complementary
the security based principales are:

         * minimize attack surface area
         * principales of least privilege
         * secure defaults
         * encrypt sensitive data
         * maintain security updates

# chapter8.Before the project

* no one knows exactly what they want
* programmers help people understand what they want (they focus on edge cases)
* always keep an open communication channel with the users of the app , because requirements are learned in feedback loop
* use a project glossory in order for everyone to understand the terms used in the project ,because each project has its own jargon 

# chapter9.Pragmatic  projects

## Different types of tests :
#### unit testing: 
* each module must pass the unit testing individualy before interating with other modules
* integration testing
* its an extension to the unit testing 
* validation and verification
* make sure we answers the user’s needs

#### performance testing
called also stress testing;making sure the software works under real world conditions
#### testing the tests
make the sure tests would catch the bugs if they happened for real

# note : 
## not a software engineer neither a software developer but u r a problem solver
