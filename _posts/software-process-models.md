---
published: false
---
## Software Process Models/ life cicle

The steps used to construct a useable and high quality software

"BARRy Bohem"
sequence of decision you made determine the history of your software
systematic approach that uses different tools
questions to ask what to do next and how long it take
it is important to know which model is proper for a particular situation
small projects work with agile, large projects need rigorous approaches
The process of choosing the model is flexiable, you may choose one model for a part in the project while choosing another model for another part.


### Traditional software engineer phases

- Requirements engineer (early error discovery save effforts and money)
		requirements elecitation
        requirements analysis
        specification
        requirements validation
        management
        
- Design (high to low level)
	architecture design
    abstruct specification
    interface design
    component design
    data structure
    algo design
    
- implementation
   reduction of complixity
   anticipation of diversity
   structuring for validation
   use of external standards
   
   
- verification & validation
	unit test
    integeration test
    system test
    
- maintenance (bug report, feature request, environmental change)
	 -corrective maintenance
     - perfective maintenance
     - adaptive maintenance
     
     complex because of regression test
     
     

Models

1) Waterfall
Sequentail steps of starting and ending the software development process, in that a step can't be initiated unless the previous one finished. Developed by W. W. Royce
![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Waterfall_model.svg/525px-Waterfall_model.svg.png)

pross:
- detecting errors early

cons:
 not flexible
 expensive change later
 

2) Spiral
increamental risk oriented model that exeutes four main phases 
- Determine objectives
- I denify and resolve risks
- Development and testing
- Plan for next iteration
developer by

![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Spiral_model_%28Boehm%2C_1988%29.svg/500px-Spiral_model_%28Boehm%2C_1988%29.svg.png)

**pross** 
Risk reduction
flexible( can add functionality at any level of the spiral)
early software production

**cons**
- require highly specific expertise for risk analysis

3) Evoultionary Prototyping Process
 An iterative model involves building system prototype based on customer requirements. It includes four main phases 
 - initial concept
 - Design and implement prototype
 - Refine Prototype
 - complete and release prototype
 
 The final product is the result of of goinf back and fourth repeaating the previous four steps until reaching customer satisfaction.
 
 **pross**
 - immediate feedback from customers
 
 **cons**
 - diffecult to plan in advance


4) Rational Unified Process (RUP)
An iterative common software model.
containd four phases:
- Inception
- Elaboration
- Construction
- Transition

![](https://en.wikipedia.org/wiki/Rational_Unified_Process#/media/File:Development-iterative.png)

**pros**
- Regular feedback 
- risk Managment

**cons**
- complex to develop
- requires expertise

5) Agile TDD( red, Green, refactor)
Highy incremental development. Test the code before writing the code
- Fail (Red phase)
- Green Phase (Write code(make the test pass))
- Refactor (modify the code for readiblity and maintainblilty)

![](http://tryqa.com/wp-content/uploads/2014/12/Test_Driven_Development_Agile_Testing.jpg)

**Pros**

**Cons**


## Selecting the right model
Depends on :

- Requirements understanding
- Expected Lifetime
- Risk
- Schedule constraints
- Interaction with customers
- Expertise


examples
- Software control systems: Pure waterfall
Domain is well understood
No customer interaction
requirements don't change dramitlly


Midcourse Correction system
Spiral or Evolutionary prototyping


Resource

[] (https://www.testingexcellence.com/iterative-incremental-development-agile/)
[Software Development process-udacity](https://www.udacity.com/course/software-development-process--ud805)

