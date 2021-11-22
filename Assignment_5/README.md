# Assignment 4

By: Alexander Høyby

</br>

## Task 1 - Models and Entailment in Propositional Logic

1. For each statement below, determine whether the statement is true or false by building the complete model table

   (a) ¬A ∧ ¬B |= ¬B\
   (b) ¬A ∨ ¬B |= ¬B\
   (c) ¬A ∧ B |= A ∨ B\
   (d) A ⇒ B |= A ⇔ B\
   (e) (A ⇒ B) ⇔ C |= A ∨ ¬B ∨ C\
   (f) (¬A ⇒ ¬B) ∧ (A ∧ ¬B) is satisfiable\
   (g) (¬A ⇔ ¬B) ∧ (A ∧ ¬B) is satisfiable

   ### a - True

   |  A  |  B  | ¬A ∧ ¬B | ¬B  | ¬A ∧ ¬B \|= ¬B |
   | :-: | :-: | :-----: | :-: | :------------: |
   |  T  |  T  |    F    |  F  |                |
   |  T  |  F  |    F    |  T  |                |
   |  F  |  T  |    F    |  F  |                |
   |  F  |  F  |    T    |  T  |      True      |

   </br>

   ### b - False

   |  A  |  B  | ¬A ∨ ¬B | ¬B  | ¬A ∨ ¬B \|= ¬B |
   | :-: | :-: | :-----: | :-: | :------------: |
   |  T  |  T  |    F    |  F  |                |
   |  T  |  F  |    T    |  T  |      True      |
   |  F  |  T  |    T    |  F  |     False      |
   |  F  |  F  |    T    |  T  |      True      |

   </br>

   ### c - True

   |  A  |  B  | ¬A ∧ B | A ∨ B | ¬A ∧ B \|= A ∨ B |
   | :-: | :-: | :----: | :---: | :--------------: |
   |  T  |  T  |   F    |   T   |                  |
   |  T  |  F  |   F    |   T   |                  |
   |  F  |  T  |   T    |   T   |       True       |
   |  F  |  F  |   F    |   F   |                  |

   </br>

   ### d - False

   |  A  |  B  | A ⇒ B | A ⇔ B | A ⇒ B \|= A ⇔ B |
   | :-: | :-: | :---: | :---: | :-------------: |
   |  T  |  T  |   T   |   T   |      True       |
   |  T  |  F  |   F   |   F   |                 |
   |  F  |  T  |   T   |   F   |      False      |
   |  F  |  F  |   T   |   T   |      True       |

   </br>

   ### e - True

   |  A  |  B  |  C  | (A ⇒ B) ⇔ C | A ∨ ¬B ∨ C | (A ⇒ B) ⇔ C \|= A ∨ ¬B ∨ C |
   | :-: | :-: | :-: | :---------: | :--------: | :------------------------: |
   |  T  |  T  |  T  |      T      |     T      |            True            |
   |  T  |  T  |  F  |      F      |     T      |                            |
   |  T  |  F  |  T  |      F      |     T      |                            |
   |  T  |  F  |  F  |      T      |     T      |            True            |
   |  F  |  T  |  T  |      T      |     T      |            True            |
   |  F  |  T  |  F  |      F      |     F      |                            |
   |  F  |  F  |  T  |      T      |     T      |            True            |
   |  F  |  F  |  F  |      F      |     T      |                            |

   </br>

   ### f - Yes

   |  A  |  B  | (¬A ⇒ ¬B) ∧ (A ∧ ¬B) | Satasfiable? |
   | :-: | :-: | :------------------: | :----------: |
   |  T  |  T  |          F           |              |
   |  T  |  F  |          T           |     Yes      |
   |  F  |  T  |          F           |              |
   |  F  |  F  |          F           |              |

   </br>

   ### g - No

   |  A  |  B  | (¬A ⇔ ¬B) ∧ (A ∧ ¬B) | Satasfiable? |
   | :-: | :-: | :------------------: | :----------: |
   |  T  |  T  |          F           |      No      |
   |  T  |  F  |          F           |      No      |
   |  F  |  T  |          F           |      No      |
   |  F  |  F  |          F           |      No      |
   |  F  |  F  |          F           |      No      |

   </br>

2. Consider a logical knowledge base with 100 variables, A<sub>1</sub>, A<sub>2</sub>, . . . , A<sub>100</sub>. This will have Q = 2<sup>100</sup>
   possible models. For each logical sentence below, give the number of models that satisfy it.
   Feel free to express your answer as a fraction of Q (without writing out the whole number
   1267650600228229401496703205376 = 2<sup>100</sup>) or to use other symbols to represent large numbers.

   Example: The logical sentence A1 will be satisfied by 1/2 Q = 1/2 \* 2<sup>100</sup> = 299 models.

   (a) A<sub>31</sub> ∧ ¬A<sub>76</sub> is satisfied by

   `1-(1-(1/2)∧2) = 1/4 Q`.

   (b) The expression A<sub>44</sub> ∧ A<sub>49</sub> ∧ A78 is satisfied by

   `1-(1-(1/2)∧3) = 1/8 Q`.

   (c) The expression A<sub>44</sub> ∨ A<sub>49</sub> ∨ A78 is satisfied by

   `3/8 Q`.

   (d) The expression A<sub>70</sub> ⇒ ¬A<sub>92</sub> is satisfied by

   `1-((1/2)∧2) = 3/4 Q`.

   (e) The expression (A<sub>7</sub> ⇔ A<sub>72</sub>) ∧ (A<sub>83</sub> ⇔ A<sub>84</sub>) is satisfied by

   `4/16 Q`.

   The expression (A<sub>7</sub> ⇔ A<sub>72</sub>) ∧ (A<sub>83</sub> ⇔ A<sub>84</sub>)\
   = (A<sub>7</sub> ⇒ A<sub>72</sub>) ∧ (A<sub>72</sub> ⇒ A<sub>7</sub>) ∧ (A<sub>83</sub> ⇒ A<sub>84</sub>) ∧ (A<sub>84</sub> ⇒ A<sub>83</sub>)\
   = (¬A<sub>7</sub> ∨ A<sub>72</sub>) ∧ (¬A<sub>72</sub> ∨ A<sub>7</sub>) ∧ (¬A<sub>83</sub> ∨ A<sub>84</sub>) ∧ (¬A<sub>84</sub> ∨ A<sub>83</sub>) is satisfied by

   `1/64 Q`

   (f) The expression ¬A<sub>9</sub> ∧ ¬A<sub>19</sub> ∧ A<sub>37</sub> ∧ A<sub>50</sub> ∧ A<sub>68</sub> ∧ A<sub>73</sub> ∧ A<sub>79</sub> ∧ A<sub>81</sub> is satisfied by

   `1/64 Q`.

   </br>

3. Consider the Wumpus world in Figure 7.2 / 6.2 . Suppose the agent starts in room in the bottom right corner, i.e. [4, 1]. The agent then moves north/upward twice, visiting the rooms [4, 2] and [4, 3]. The agent perceives a breeze in [4, 1] and [4, 3], but not in [4, 2]. From these percepts, we are interested in determining the possible configuration of pits in the adjacent rooms, i.e. [3, 1], [3, 2], [3, 3] and [4, 4].

   Build the full model table of all possible worlds by constructing a truth table with the variables P3,1,P3,2, P3,3 and P4,4, each of which specifies whether there is a pit in a particular room. Mark the worlds in which the knowledge base is true, i.e. the pit configurations that are consistent with the perceived breezes. Additionally, mark the worlds in which each of the following sentences is true:

   α1 = “There is no pit in [3, 2]”.\
   α2 = “There is a pit in [4, 4]”.\
   α3 = “There is no a pit in [4, 4]”.\
   α4 = “There is a pit in [3, 3] or [4, 4]”.

   Based on the truth table, which of the sentences α1, α2, α3 and α4 can you conclude are entailed by the knowledge base? I.e., specify which of the following are true: KB |= α1, KB |= α2, KB |= α3 and KB |= α4.

   </br>

## Task 2 - Resolution in Propositional Logic

1.  Convert each of the following sentences to Conjunctive Normal Form (CNF).

    **(a) A ∨ (B ∧ C ∧ ¬D)**

    `(A ∨ B) ∧ (A ∨ C) ∧ (A ∨ ¬D)` - _Distributive_

    **(b) ¬(A ⇒ ¬B) ∧ ¬(C ⇒ ¬D)**

    `¬(¬A ∨ ¬B) ∧ ¬(¬C ∨ ¬D)` - _Implication_\
    `(¬¬A ∧ ¬¬B) ∧ (¬¬C ∧ ¬¬D)` - _de Morgan’s_\
    `(A ∧ B) ∧ (C ∧ D)` - _Double negation_\
    `A ∧ B ∧ C ∧ D` - _Associativity_

    **(c) ¬((A ⇒ B) ∧ (C ⇒ D))**

    `¬((¬A ∨ B) ∧ (¬C ∨ D))` - _Implication_\
    `¬(¬A ∨ B) ∨ ¬(¬C ∨ D)` - _de Morgan’s_\
    `(¬¬A ∧ ¬B) ∨ (¬¬C ∧ ¬D)` - _de Morgan’s_\
    `(A ∧ ¬B) ∨ (C ∧ ¬D)` - _Double negation_\
    `((A ∧ ¬B) ∨ C) ∧ ((A ∧ ¬B) ∨ ¬D)` - _Distributive_\
    `(A ∨ C) ∧ (¬B ∨ C) ∧ (A ∨ ¬D) ∧ (¬B ∨ ¬D)` - _Distributive_

    **(d) (A ∧ B) ∨ (C ⇒ D)**

    `(A ∧ B) ∨ (¬C ∨ D)` - _Implication_\
    `(A ∨ (¬C ∨ D)) ∧ (B ∨ (¬C ∨ D))` - _Distributive_\
    `(A ∨ ¬C ∨ D) ∧ (B ∨ ¬C ∨ D)` - _Associativity_

    **(e) A ⇔ (B ⇒ ¬C)**

    `(A ⇒ (B ⇒ ¬C)) ∧ ((B ⇒ ¬C) ⇒ A)` - _Implication_\
    `(¬A ∨ (¬B ∨ ¬C)) ∧ (¬(¬B ∨ ¬C) ∨ A)` - _Implication_\
    `(¬A ∨ ¬B ∨ ¬C) ∧ (¬(¬B ∨ ¬C) ∨ A)` - _Distributive_\
    `(¬A ∨ ¬B ∨ ¬C) ∧ ((B ∧ C) ∨ A)` - _de Morgan’s_\
    `(¬A ∨ ¬B ∨ ¬C) ∧ (B ∨ A) ∧ (C ∨ A)` - _Distributive_

    </br>

2.  Consider the following Knowledge Base (KB):

    - (X ∧ ¬Y ) ⇒ ¬B
      - ¬X ∨ Y ∨ ¬B
    - ¬X ⇒ C
      - X ∨ C
    - B ∧ ¬Y
    - A ⇒ ¬C
      - ¬A ∨ ¬C

    Use resolution to show that KB |= ¬A

    1. `¬X ∨ Y ∨ ¬B`
    2. `X ∨ C`
    3. `B`
    4. `¬Y`
    5. `¬A ∨ ¬C`

    Combining 1, 2, 3 and 4 Gives us:\
    `(¬X ∨ Y ∨ ¬B) ∧ (X ∨ C) ∧ (¬A ∨ ¬C) ∧ B ∧ ¬Y`

    ```
    6 = 1 + 2 = Y ∨ ¬B ∨ C    => (Y ∨ ¬B ∨ C) ∧ (¬A ∨ ¬C) ∧ B ∧ ¬Y
    7 = 3 + 6 = Y ∨ C         => (Y ∨ C) ∧ (¬A ∨ ¬C) ∧ ¬Y
    8 = 4 + 7 = C             => C ∧ (¬A ∨ ¬C)
    9 = 5 + 8 = ¬A            => ¬A
    ```

 </br>

3. (Question borrowed from AIMA 3rd edition.)
   A propositional 2-CNF expression is a conjunction of clauses, each containing exactly 2 literals, e.g.,

   (A ∨ B) ∧ (¬A ∨ C) ∧ (¬B ∨ D) ∧ (¬C ∨ G) ∧ (¬D ∨ G).

   (a) Prove using resolution that the above sentence entails G.

   `(A ∨ B) ∧ (¬A ∨ C) ∧ (¬B ∨ D) ∧ (¬C ∨ G) ∧ (¬D ∨ G)` - _Complement A_\
   `(B ∨ C) ∧ (¬B ∨ D) ∧ (¬C ∨ G) ∧ (¬D ∨ G)` - _Complement B_\
   `(C ∨ D) ∧ (¬C ∨ G) ∧ (¬D ∨ G)` - _Complement C_\
   `(D ∨ G) ∧ (¬D ∨ G)` - _Complement D_\
   `(G ∨ G)` - _Idempotent_\
   `G`

   (b) Two clauses are semantically distinct if they are not logically equivalent. How many emantically distinct 2-CNF clauses can be constructed from n proposition symbols?

   `2n^2 – 2n`

   (c) Using your answer to (b), prove that propositional resolution always terminates in time polynomial in n given a 2-CNF sentence containing no more than n distinct symbols.

   `?`

   (d) Explain why your argument in (c) does not apply to 3-CNF.

   `?`

 </br>

## Task 3 - Representations in First-Order Logic

1. Consider a vocabulary with the following symbols: (Question borrowed from AIMA 3rd edition.)\
   _Occupation(p, o)_ : Predicate. Person p has occupation o.\
   _Customer(p1, p2)_ : Predicate. Person p1 is a customer of person p2.\
   _Boss(p1, p2)_ : Predicate. Person p1 is a boss of person p2.\
   _Doctor, Surgeon, Lawyer, Actor_ : Constants denoting occupation.\
   _Emily, Joe_ : Constants denoting people.

   Use these symbols to write the following assertions in first-order logic:

   (a) Emily is either a surgeon or a lawyer.

   `Occupation(Emily, Surgeon) ∨ Occupation(Emily, Lawyer) `

   (b) Joe is an actor, but he also holds another job.

   `Occupation(Joe, Actor) ∨ ∃o: Occupation(Joe, o) ∧ ¬(o = Actor)`

   (c) All surgeons are doctors.

   `∀p: (Occupation(p, Surgeon) ⇒ Occupation(p, Doctor))`

   (d) Joe does not have a lawyer (i.e., is not a customer of any lawyer).

   `¬∃p: (Customer(Joe, p) ∧ Occupation(p, Lawyer))`

   (e) Emily has a boss who is a lawyer.

   `∃p: (Boss(p, Emily) ∧ Occupation(p, Lawyer))`

   (f) There exists a lawyer all of whose customers are doctors.

   `∃p1 ∀P2: Occupation(p1, Lawyer) ∧ (Customer(p2, p1) ⇒ Occupation(p2, Doctor))`

   (g) Every surgeon has a lawyer.

   `∀p1 ∃p2: Occupation(p1, Surgeon) ⇒ (Customer(p1, p2) ∧ Occupation(p2, Lawyer))`

   <!-- The natural connective for ∀ is ⇒. -->
   <!-- The natural connective for ∃ is ∧ -->

   </br>

2. Consider a first-order logical knowledge base that describes worlds containing movies, actors, directors and characters. The vocabulary contains the following symbols:

   - _PlayedInMovie(a,m)_: predicate. Actor/person a played in the movie m
   - _PlayedCharacter(a,c)_: predicate. Actor/person a played character c
   - _CharacterInMovie(c,m)_: predicate. Character c is in the movie m.
   - _Directed(p,m)_: person p directed movie m.
   - _Male(p)_: p is male
   - _Female(p)_: p is female

   (a) The character “Batman” was played by Christian Bale, George Clooney and Val Kilmer.

   `PlayedChar(Bale, "Batman") ∧ PlayedChar(Clooney, "Batman") ∧ PlayedChar(Kilmer, "Batman")`

   (b) The character “Batman” was played by male actors.

   `∀a: PlayedChar(a, "Batman") ⇒ Male(a)`

   (c) The character “Batwoman” was played by female actresses.

   `∀a: PlayedChar(a, "Batwoman") ⇒ Female(a)`

   (d) Heath Ledger and Christian Bale did not play the same characters.

   `¬∀c: PlayedChar(Ledger, c) ∧ PlayedChar(Bale, c)`

   (e) In all “Batman” movies directed by Christopher Nolan, Christian Bale played the character Batman (tip: note that in this case Batman is a character of the movie, not the name of the movie).

   `∀m: Directed(Nolan, m) ∧ CharacterInMovie("Batman", m) ⇒ PlayedChar(Bale, "Batman"))`

   (f) The Joker and Batman are characters that appear together in some movies.

   `∃m: CharacterInMovie(Batman,m) ∧ CharacterInMovie(Joker,m)`

   (g) Kevin Costner directed and starred in the same movie.

   `∃m: Directed(Costner,m) ∧ PlayedInMovie(Costner,m)`

   (h) George Clooney and Tarantino never played in the same movie and Tarantino never directed a
   film that George Clooney played.

   `∀m: PlayedInMovie(Clooney,m) ⇒ ¬(PlayedInMovie(Tarantino,n) ∨ Directed(Tarantino,n))`

   (i) Uma Thurman is female actress who played a character in some movies directed by Tarantino

   `∃m: Directed(Tarantino,m) ∧ PlayedInMovie(Thurman,m)`

   </br>

3. Arithmetic assertions can be written using FOL. Use the predicates (<,≤,≠,=), usual arithmetic operations as function symbol (+,-,_×_,/), biconditionals to create new predicates, and integer number constants to express the following statements in FOL:

   (a) An integer number x is divisible by y if there is some integer z less than x such that x = z × y (in other words, define the predicate Divisible(x, y)).

   `∀x,y: Divisable(x,y) ⇔ ∃z: (z ≤ x) ∧ (x = x * y)`

   (b) A number is even if and only if it is divisible by 2 (define the predicate Even(x)).

   `∀x: Even(x) ⇔ Divisable(x,2)`

   (c) An odd number is not divisible by 2 (define the predicate Odd(x)).

   `∀x: Odd(x) ⇔ ¬Divisable(x,2)`

   (d) The result of summing an even number with 1 is an odd number (define the predicate Odd(x)).

   `∀x: Odd(x) ⇔ ∃y: Even(y) ∧ (x = y + 1)`

   (e) A prime number is divisible only by itself (define the predicate Prime(x)).

   `∀x: Prime(x) ⇔ ∀y: ¬Divisable(x,y) ∧ (x ≠ y)`

   (f) There is only one even prime number.

   `∀x ∃y: Prime(x) ∧ Even(x) ⇔ y = x`

   (g) Every integer number is equal to a product of prime numbers. (you can use sum\_{i=1}∧{k} pk to express a product of numbers, or use . . . to express a repeating pattern, like p<sub>1</sub>, . . . , p<sub>n</sub>, meaning p<sub>1</sub>, p<sub>2</sub>, p<sub>3</sub> until p<sub>n</sub>).

   `∀x ∈ ℤ: x = sum_{i=1}∧{k}pₖ ∧ Prime(pₖ)`

   </br>

## Task 4 - Resolution in First-Order Logic

1. Find the unifier (θ) – if possible – for each pair of atomic sentences. Here, _Owner(x, y)_, _Horse(x)_ and
   _Rides(x, y)_ are predicates, while _FastestHorse(x)_ is a function that maps a person to the name of
   their fastest horse:

   (a) Horse(x) . . . Horse(Rocky)

   `θ = {x/Rocky}`

   (b) Owner(Leo, Rocky) . . . Owner(x, y)

   `θ = {x/Leo, y/Rocky}`

   (c) Owner(Leo, x) . . . Owner(y, Rocky)

   `θ = {y/Leo, x/Rocky}`

   (d) Owner(Leo, x) . . . Rides(Leo, Rocky)

   `Not possible - Predicates not matching`

   (e) Owner(x, FastestHorse(x)) . . . Owner(Leo, Rocky)

   `Not possble - FastestHorse(x) does not match with Rocky`

   (f) Owner(Leo, y) . . . Owner(x, FastestHorse(x))

   `θ = {x/Leo, y/FastestHorse(Leo)}`

   (g) Rides(Leo, FastestHorse(x)) . . . Rides(y, FastestHorse(Marvin))

   `θ = {y/Leo, x/Marvin}`

   </br>

2. Using the predicates P hilosopher(x), StudentOf(y, x), W rite(x, z), Read(y, z) and Book(z) perform skolemization with the following expressions:

   (a) ∃x∃y: Philosopher(x) ∧ StudentOf(y,x)

   `Philosopher(C1) ∧ StudentOf(C2,C1)`

   (b) ∀ y,x: Philosopher(x) ∧ StudentOf(y,x) → [∃z: Book(z) ∧ Write(x,z) ∧ Read(y,z)]

   `∀ y,x: Philosopher(x) ∧ StudentOf(y,x) → [Book(C(x,y)) ∧ Write(x,C(x,y)) ∧ Read(y,C(x,y))]`

   </br>

3. Use resolution to prove SuperActor(Tarantino) given the information below. You must first convert each sentence into CNF. Feel free to show only the applications of the resolution rule that lead to the desired conclusion. For each application of the resolution rule, show the unification bindings, θ. We are using in this case the same predicates of Exercise 3.1 (movies, actors, etc).

   - ∀x: SuperActor(x) ↔ [∃m: PlayedInMovie(x,m) ∧ Directed(x,m)]
   - ∀m: Directed(Tarantino,m) ↔ PlayedInMovie(UmaThurman,m)
   - ∃m: PlayedInMovie(UmaThurman,m) ∧ PlayedInMovie(Tarantino,m)

   (a) Show all the steps in the proof (or the diagram).

   1. **∀x: SuperActor(x) ↔ [∃m: PlayedInMovie(x,m) ∧ Directed(x,m)]**

   `∀x: (SuperActor(x) → [∃m: PlayedInMovie(x,m) ∧ Directed(x,m)]) ∧ ([∃m: PlayedInMovie(x,m) ∧ Directed(x,m)] → SuperActor(x))` - _Biconditional_\
   `∀x: (¬SuperActor(x) ∨ [∃m: PlayedInMovie(x,m) ∧ Directed(x,m)]) ∧ ¬([∃m: PlayedInMovie(x,m) ∧ Directed(x,m)] ∨ SuperActor(x))` - _Implication_\
   `∀x: (¬SuperActor(x) ∨ [∃m: PlayedInMovie(x,m) ∧ Directed(x,m)]) ∧ ([∀m: ¬PlayedInMovie(x,m) ∨ ¬Directed(x,m)] ∨ SuperActor(x))` - _de Morgan_\
   `∀x: (¬SuperActor(x) ∨ [PlayedInMovie(x,C) ∧ Directed(x,C)]) ∧ ([∀m: ¬PlayedInMovie(x,m) ∨ ¬Directed(x,m)] ∨ SuperActor(x))` - _Skolemization_\
   `(¬SuperActor(x) ∨ [PlayedInMovie(x,C) ∧ Directed(x,C)]) ∧ ([¬PlayedInMovie(x,m) ∨ ¬Directed(x,m)] ∨ SuperActor(x))` - _Quantifiers_\
   `(¬SuperActor(x) ∨ PlayedInMovie(x,C)) ∧ (¬SuperActor(x) ∨ Directed(x,C)) ∧ (¬PlayedInMovie(x,m) ∨ ¬Directed(x,m) ∨ SuperActor(x))` - _Distribute_

   2. **∀m: Directed(Tarantino,m) ↔ PlayedInMovie(UmaThurman,m)**

   `∀m: Directed(Tarantino,m) ↔ PlayedInMovie(UmaThurman,m)` - _Initial_\
   `∀m: Directed(Tarantino,m) → PlayedInMovie(UmaThurman,m) ∧ PlayedInMovie(UmaThurman,m) → Directed(Tarantino,m)` - _Biconditional_\
   `∀m: ¬Directed(Tarantino,m) ∨ PlayedInMovie(UmaThurman,m) ∧ ¬PlayedInMovie(UmaThurman,m) ∨ Directed(Tarantino,m)` - _Implication_\
   `(¬Directed(Tarantino,m) ∨ PlayedInMovie(UmaThurman,m)) ∧ (¬PlayedInMovie(UmaThurman,m) ∨ Directed(Tarantino,m))` - _Quantifiers_

   3. **∃m: PlayedInMovie(UmaThurman,m) ∧ PlayedInMovie(Tarantino,m)**

   `∃m: PlayedInMovie(UmaThurman,m) ∧ PlayedInMovie(Tarantino,m)` - _Initial_\
   `PlayedInMovie(UmaThurman,C) ∧ PlayedInMovie(Tarantino,C)` - _Skolemization_

   We want to prove `SuperActor(Tarantino)` by contradiction:\
   **KB is:**

   1. `(¬SuperActor(x) ∨ PlayedInMovie(x,C))`
   2. `(¬SuperActor(x) ∨ Directed(x,C))`
   3. `(¬PlayedInMovie(x,m) ∨ ¬Directed(x,m) ∨ SuperActor(x))`
   4. `(¬Directed(Tarantino,m) ∨ PlayedInMovie(UmaThurman,m))`
   5. `(¬PlayedInMovie(UmaThurman,m) ∨ Directed(Tarantino,m))`
   6. `PlayedInMovie(UmaThurman,C)`
   7. `PlayedInMovie(Tarantino,C)`

   </br>

   Proof:

   8. `¬SuperActor(Tarantino)`
   9. 5 + 3 = \
      `(¬PlayedInMovie(UmaThurman,m) ∨ Directed(Tarantino,m)) | ¬PlayedInMovie(x,m) ∨ ¬Directed(x,m) ∨ SuperActor(x)`\
      `θ = {x/Tarantino, m/m}`\
      Result: `¬PlayedInMovie(UmaThurman,m) ∨ ¬PlayedInMovie(Tarantino,m) ∨ SuperActor(Tarantino)`
   10. 9 + 6 = \
       `¬PlayedInMovie(UmaThurman,m) ∨ ¬PlayedInMovie(Tarantino,m) ∨ SuperActor(Tarantino) | PlayedInMovie(UmaThurman,C)`\
       Result: `¬PlayedInMovie(Tarantino,m) ∨ SuperActor(Tarantino)`
   11. 10 + 7 = \
       `¬PlayedInMovie(Tarantino,m) ∨ SuperActor(Tarantino) | PlayedInMovie(Tarantino,C)`\
       Result: `SuperActor(Tarantino)`
   12. 11 + 8 = \
       `SuperActor(Tarantino) | ¬SuperActor(Tarantino)`\
       Result: Contradiction. ⊥

   </br>

   (b) Translate the information given in FOL into English (or Norwegian) and describe in high level
   the reasoning you could apply in English to have the same result (in other words, describe a
   proof of the result in natural language).

   We know that beeing a super actor means that you are both directing and acting in a film by 1, 2 and 3. We also know by 4 and 5 that UmaThurman is acting iff it is directed by Tarantino. From 6 and 7, we know that there is a movie that both UmaThurman and Tarantino acting. This means, since UmaThurman is acting, Tarantino must be Directing. Tarantino must therefore be acting and playing and is therefore a SuperActor.
