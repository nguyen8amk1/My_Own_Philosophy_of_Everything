# RANDOM QUOTES (that should be added to some topic):

## IMPORTANT: KNOW YOUR TOOLS WELL 
	Stick to a tool and have good performance in it 
	Can operate fast on it
    -> a good measurements is:
        you can create a WORKING PROTOTYPE of YOUR IDEAS in 30MINS - 3 DAYS 

## PERFECT IS LOTS OF SMALL THINGS DONE WELL 

## YOU SHOULD BE ABLE TO MAKE YOUR SOFTWARE DO WHAT YOU WANT IT TO DO 
    (within the reasonable limits of its capabilities)
    -> the KEY to ATTAINING THIS POWER: 
        -> UNDERSTANDING the FUNDAMENTALS of: 
            + WHAT the software does 
            + HOW It works
    -> From the book: [How Linux Works](./notes/books/How_Linux_Works.md)

## ***You only USE something(tool) when you need its BENEFITS
	-> Not use it just because you can use it, or other tell you to ...

## Things in life happens in (solution) pattern, a lot of patterns applies to almost every aspect of our lives (economics, decisions, coding, math, ...)
	-> learning general patterns can help you solve most of the problems in most aspect of life
	-> a good language to learning these patterns is Mathematics
	-> Mathematics give you: 
		+ an abstract representation of the patterns 
		+ the tools:
			+ to prove the correctness of the patterns 
			+ to predicts the outcome of the patterns
			+ to create new patterns 
			+ to check the similarity between different fields then apply the same pattern to solve them (Category theory ??)
	-> Able to ABSTRACTLY RECOGINIZE PATTERNS is one of the most powerful things ever (along with all the tools/operations you can apply to the patterns (deduce new patterns, ...))

	-> Question: 
		-> WHAT ARE THE PROPERTIES THAT WE CAN USE TO IDENTIFY PATTERNS ? 
			vd: the similarity of the rules of managing between finantial portfolio and technical portfolio is almost 1 to 1 
			....

		-> HOW TO ABSTRACT IT THE CONCRETE PATTERNS INTO GENERAL PATTERNS ? 
			....

		-> HOW TO PROVE THAT THE ABSTRACT PATTERN IS APPLICABLE TO SOME RANDOM FIELDS ? (Mathematically?)
			....

		-> Does category theory is the answers to all of these questions ?? 
			Category theory is more about how we structure knowledge rather than how knowledge actually are,
			focus on relation (morphism), not content (object)  
			->  prove things using relation between them so the actual object does not matter 
				as long as the foundation relationship between them holds  
			....

## THE PROCESS OF FULLY UNDERSTAND ANYTHING:
	If you keep using the [criteria of concepts](./frameworks//things_you_need_to_know_before_choosing_tools.md) on things you wanted to learn:
		an keep running down the rabbit hole: 
			vd: you disect concepts A into: 
				it's:
					Type: B
					Unique Features: C
					How to use it: D 
				-> Each will be come a concepts on its own 
					-> RECURSIVELY GO DOWN THE RABBIT HOLE 
		-> [good enough mindset](./frameworks/good_enough_philosophy.md) is a must to get anything done on time
			-> since it give you a STOPPING POINT at digging to actually REST and USE the gained concepts 

## THE SKILL TO GETTING THINGS DONE WITHOUT KNOWING ALL THE DETAILS OF THE SYSTEM YOU ARE CURRENTING WORKING ON:
	vd: You already know CONCEPTUALLY how to solve the problem 
		-> the problem abstractly solved using math or something like that 

	-> now only need to implement it into the real-world :)) 

	BUT, to implement it in the real world is NOT very STRAIGHT-FORWARD 
	since you need an environment that match the mathematical model (abstract environment) that you use to solve the problem in 

	-> there a lot of setup when cause things are get in the way 
	-> So the setting up part is not needed to remember, they are just preparation

	-> The core is already in your head 

	-> SOLVE THE PROBLEM CONCEPTUALLY, IMPLEMENTATION IS NOW JUST DRUDG WORK

	vd: you already now how to move a circle according to time
		-> you can do that in any language(js, node, java,...), environment(web canvas, DOM, desktop, ...)


## ABSTRACTION: IS KINDA LIKE SUBSTRACTION 
	-> getting rid of the details 

oop abstract away the wrong thing (which makes it hard to do things in parallel) 
	-> it abstract away data races

data races: 
	-> data mutation
	-> data sharing 

Category theory is the highest language of all the programming languages

All the problems, or study seems the same because we see them in the same structure -> the choppable structure (that we evolve to solve without even noticing it)

Category theory is more about how our mind reason thing in structure 
	-> not about mathematics, or physics 
	-> not learn what things are
	-> but learn about how we can study them 


---------------------------------------
Tools:
	+ Abstraction: getting rid of unnecessary details


	+ Composition: 
	+ Identity
	-> CATEGORY THEORY: the above 2 

Definitions: 
	Category definition is hard to precisely define 
		-> it just a bunch of objects :v 
		-> with morphims 
		-> 2 primitives:
			Object definition is also hard to precisely define :v 
				-> it's a primitive in category theory
				-> has no properties

			Morphism definition is also hard to precisely define :v
				-> it's also a primitive in category theory
				-> has no properties
				-> it's an arrow with a beginning and an end 
			-> Object is used to mark the two ends of arrow

		-> 2 properties: 
			Composition: 
				which state that if: 
					a f-> b g-> c  
					-> there MUST EXIST a composition of g.f = a -> c
			The PRIMITIVE don't contain information 

			Cause the information is contained in the COMPOSITION
			-> composition table: contains all the possible compositions of the consecutive arrows

			Identity:
				have:
					right identity: 
					left identity:  
				it's like mult by 1 

				-> every object MUST have a LOOP  
			
			Associative: 
				-> h.(g.f) = (h.g).f

	-> Programming is a category 
		-> 2 primitives: 
		+ Objects = Types (set of values)
		+ Morphisms = Functions (mapping from 1 set to another set)

	NOTE: 
		Examining Set in Set Theory: 
		we can forget about What's the Sets contains, what the functions do as long 
		as we have a COMPOSITION TABLE  
			-> since it's the only place that have information
			-> give a new, more abstract way of looking at things 
		
		****: 
			Category theory give us a way to understand Set 
			without actually look into the set
			just look at how they are connected with arrows (in COMPOSITION TABLE)
			-> the ultimate encapsulation -> only shows the interface 

-----------------------------------------------------------------------------
Denominal semantics: ?? 
Function: 
	pure: a pure function is a function that can be memoize 
		-> means can be transform into a lookup table 
		-> is the lowest level of abstraction that can be compose to build more complex things

	total: return an output for every possible input 
	
	relation: 
		a subset of Cartesion product (basically a region in Catergion plane) 
		condition: 
			n input can be mapped to 1 output 
				-> but not inverse 

		The set of input called domain 
		-> the set of output (could be smaller since not map 1-1) called codomain

		Diretionality: 
			The relation have a direction from input to output
			and it's not always can go backward 
	Note: 
		codomain and image 
		x^2: R -> R 
			-> R is the domain 
			-> R is the codomain 
			-> and the image is [0, +inf]
		-> image is a subset of the codomain 


	isomorphism: a function that is invertable 
		g.d = ida
		f.g = idb
		-> f is isomorphism if there is a g thoa man dieu kien tren 
	-> not all function are isomorphism: 
		because of 2 reasons: 
			collapse: multiple input corresponse to a single output
				-> abstraction ?? 
			the image is smaller than the codomain 
				-> modeling ?? 

	injective (don anh): map 1-1 -> no collapse 
	surjective (toan anh): image = codomain  

	-> if injective and surjective => it's an isomorphism

	Note: 
		in category theory we use Greek not Latin 
		-> injective function = monomorphism 
		-> surjective function = epimorphism 
	
	Because the only tools we have in category theory is:
		identity
		composition
		-> the whole point is not look into the element
		-> but the morphism 

	epimorphism: 
		given g1, g2 is different function
		for all c, for all g1,g2 ::b->c   g1.f = g2.f => g1 = g2
		-> express the surjective function without looking into the elements
		-> but the morphism 
		-> X f-> Y g1,g2=> Z 

	monomorphism: 
		given g1, g2 is different function
		for all c, for all g1,g2 :: c->a   f.g1 = f.g2 => g1 = g2
		-> Z g1,g2=> Y f-> X 



----
type: 
	Product (nhan)
		-> conjunction
	Sum (cong)
		-> disjunction 
	Exponentials (mu): 

-------diagrammatic reasoning------
Visual programming done right based on diagrammatic reasoning 

# diagrammatic reasoning: 
	state machines: behaviour modeling  
	Petri nets : modeling architecture (very cool)
	string diagrams: something about abstraction ??  
	category theory:  

# Petri Net: graphical programming language 
	primitives: 
		place: o
			-> condition
			-> store data -> resource 
		token: .
		arc: ->
			-> connect: transitions and places   
		transition: |
			-> turn resource into other resource 
			can: 
				fire: input token 
				consume: input token
				produce: output token 

	represent: some sort of system
		Token = resource 
		Place = container that hold resources of a given type 
		Transition = process that convert resource from one type to another 
		Arc = is the connection between Place(Container) and Transition(Process), 
			  deliver Token (resource)

	reachability:  

# Formal Logic: 
    IS THE KEY TO SOLVE SOME NONSENSE PROBLEM SUCH AS:
        apple + apple = car
        -> apple + banana = ? 
        => WHATTTTTTTT :v 

# Questionable (myown) statement:  
	Polymorphism is for interfacing(adapt with different devices, object types might be created in the future), and should not run a loop (process data): 
	Data processing should be data oriented way, or functional (parallel) ??  

# Backtracking have something to do with Set theory: 
	vd: visisted values is not gonna be chosen to use in the next step 
	total = {1, 2, 3, 4}
	visited = {1, 2}
	keep_chosen = total - visited = {3, 4}
	-> SET THEORY
	-> I think there is more to it -> KEEP RESEARCHING 

# How to make friends: 
	Important keyword: Wiggle room 

# Shouldn't store something that can be calculated 
	-> Shouldn't remember theory that can be derive from other theory 
		-> Remember: 
			+ building block 
			+ HOW to COMPOSE them 

# Keep things relative, rather than absolute
	-> one way dependencies only, not both ways 

# W questions
	The What, Why, How, When each represents a level of abstraction
		-> depends on the approach to learning/understanding (top down, bottom up)
		-> You have different ORDER to answering these questions 

	vd: 
		What the function does ? 
		How the function does it ? 

		What > How (what is higher level than how)

	The ordering from high to low: 
		When > Why > What > How 

# UNEDITED MATERIAL
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
a particular class of diagram: 
	with 1 input and 1 output

numbers as diagram is a useful syntactic sugar 
	one for each natural number 
	the syntactic sugar actually multiply the input with the natural number it represent  

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
THE POWER OF CATEGORY THEORY: 
	Category theory: the minimalistic language for describing COMPOSITION
	focus on morphism instead of objects 

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Mathematic is bottom up -> i need to know a heap of math before actually solving problem :v 
						-> can't wait til need and then learn it :)) 

	vd: Linear algebra is teaching the bottom up way: 
		-> it's like doing assembly :))  
		-> none of it make sense if you're new :)) 

Programming is typically top down 

:: type is a theorem, program is the prove of that theorem 

How to think like a mathmetician and profit from that: 

CT and programming relation:  
	Category = Programming Language 
	Object = Type 
	Morphism = Static method f(a: A): B 

Object represent real world thing is non-sense: 
Define not just interface but also algebraic properties required of implementation

Represent method as object: Exponential

Functor is basically a map that maps between data structure of objects 
	-> essentially it maps between category
	-> can map between programming language 
	-> if stay in 1 language -> endofunctor 

Category theory in programming is all about: INTERFACES DONE RIGHT 	

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Category rules is very general but it still very restrictive 

Communative diagram:

Functor: change perspective 
	2 things: 
		function on: 
			+ object : turn object in C into object in D
				vd: A= F(A), B = F(B)
			+ morphism: turn morphism in c into morphism in D
				vd: A f-> B == F(A) F(f)-> F(B)
				
	2 requirements: 
		+ identity preservation
		+ composition preservation 

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
ABSTRACTING OVER TYPE 
Generic types: 
	functions on types, type constructor:
		vd: in c++, vector is more like a function -> takes int input and return an vector<int> output
	systematic construction of types = algebraic data types
		-> need a way to write expression on types in order to create function implementation
		-> algebraic data types: building valid expression from types not values ?? 
	Generic algorithm: 
		polymorphic functions working on generic types

The power of composition:
	Define:
		primitive things 
		ways of composing things  

Unit: the primitive 

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Limit of Finite State Machines:  
	+ State space explosion 
	+ State transitions either fully dependent or fully indepedent 
	+ Often infinite representation

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Petri net is for multitasking and synchronization 
	-> not for program and data flow 

Petri net have 3 ways to deal with contention (tranh chap):  
	escort: 
	inhibitor: 
		-> these 2 serve the same purpose (i guess) :v
	done indication: deal with finite time transitions

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
contracts: check the type of the input
guarded function: function use contracts to validate input  
-> 2 of these -> category 

NOTE: 
	object in category theory is not explicitly the object in object oriented programming 
	-> it does relate but in very subtle ways

	-> the object is more of the contract 
	-> the morphism is the guarded function 

morphism: act on the object and return new object 
functors: act on both the object and morphism, return new object and new morphism 

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Abstract thinking: 
	see the similarity
	-> identify what is needed
	-> signing a name to something more complex 

Concrete thinking: 
	see the different 
	-> how it is done

There are no exact approach 
	some time bottom up (concrete to abstract) 
	some time top down (abstrarct to concrete)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
analogical comparison of cases: 
	aligning two knowledge representations, 
	then noticing where their structure matches/overlaps, noting matching features 
	ignoring irrelavant details

-> create a data base of these general cases:  

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Category theory:
	useful when you want to solve a problem in 1 realm but don't have the right tools to solve a problem 
		-> transport the problem to different realm, to see the problem in real light, the solution may become easier.  

	-> category act as the bridge between realms.
	each realm has: 
		object: sets, groups, ...
		relation: functions, homophorism
		ways: composition, associativity

	it's all about the relationship


[Computer programming concepts](./notes/books/Concepts_Techniques_Models_of_Computer_Programming.md): 
**"One does NOT programs with MODEls,
But with:
    + programming CONCEPTS  
    + WAYS to COMBINE the programming CONCEPTS"
