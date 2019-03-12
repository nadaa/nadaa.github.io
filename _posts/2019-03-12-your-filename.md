---
published: false
---

## Software Process Models/ life cicle

I am using this post to summerize my thoughts on Software development course from Udacity. This are notes of lessons(1 & 2).

Software development is a very complex process which combines various skills such as management, estimation, design solution, coding, testing, optimization, maintenance,..etc.
Good software that is built to sustain and to be used.
**Barry Bohem** defines the software development process as
"A sequence of decision you made determine the history of your software
A systematic approach that uses different tools
Questions to ask what to do next and how long it take
It is important to know which model is proper for a particular situation
Small projects work with agile, large projects need rigorous approaches
The process of choosing the model is flexible, you may choose one model for a part in the project while choosing another model for another part."



### Traditional software engineer phases

- Requirements engineer (early error discovery)
	- Requirements elecitation
    - Requirements analysis
    - Specification
    - Requirements validation
    - Management
        
- Design (high to low level)
	- Architecture design
    - Abstruct specification
    - Interface design
    - Component design
    - Data structure
    - Algorithm design
    
- Implementation
   - Reduction of complixity
   - Anticipation of diversity
   - Structuring for validation
   - Use of external standards
   
   
- Verification & validation
	- Unit test
    - Integeration test
    - System test
    
- Maintenance (bug report, feature request, environmental change)
	 - corrective maintenance
     - perfective maintenance
     - adaptive maintenance
     
 Maintenance is complex because of the regression test which is a test that runs with any change made to assure the software remains applicable all the time.
     
    

**Models**

**1) Waterfall**
Sequentail steps of starting and ending the software development process, in that a step can't be initiated unless the previous one finished. Developed by W. W. Royce
![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Waterfall_model.svg/525px-Waterfall_model.svg.png)

**pross**:
- detecting errors early

**cons**:
- not flexible
- expensive change later
 

**2) Spiral**
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

**3) Evoultionary Prototyping Process**
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

**4) Rational Unified Process (RUP)**
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

**5) Agile TDD( red, Green, refactor)**
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


**Examples**
- Software control systems: Pure waterfall
Domain is well understood
No customer interaction
requirements don't change dramitlly


Midcourse Correction system
Spiral or Evolutionary prototyping


## Resource

[Software Development process-udacity](https://www.udacity.com/course/software-development-process--ud805)
