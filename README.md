Download Link: https://assignmentchef.com/product/solved-cse240-homework-13-scheme-higher-order-functions
<br>



<h1>Introduction</h1>

The aim of this assignment is to make sure that you understand and are familiar with the concepts covered in the lectures.  By the end of the assignment, you should have

<ul>

 <li>Scheme higher order functions</li>

 <li>strong concept of logic / declarative paradigm; strong concept of facts, rules, and questions in Prlog.</li>

 <li>Basic recursive in Prolog.</li>

</ul>

<strong>Reading</strong>: Text Chapter 5 and lecture slides. Also read Text Appendix B.4 Prolog Tutorial

You are expected to do the majority of the assignment outside the class meetings.   Should you need assistance, or have questions about the assignment, please contact the instructor or the TA during their office hours.

You are encouraged to ask and answer questions on the course discussion board.  (However, <strong>do not share your answers</strong> in the course discussion board.)

Practice Exercises (no submission required)

<ol>

 <li>Answer the multiple choice questions in text section 5.9 that have been covered in the lectures.</li>

</ol>

<ul>

 <li>Complete the questions 2 through 5 in text section 5.9.</li>

 <li>Look up the Unix command table in Appendix B.1 and read the Prolog tutorial in B.4.</li>

 <li>Log onto general.asu.edu and execute the Unix commands and Prolog exercises.</li>

 <li>Follow the Prolog tutorial in Text Appendix B.4 or the tutorials given in the course Web site, start GNU Prolog and try following simple programs (build-in functions). Don’t forget the <strong>period</strong> at the end of the statement.</li>

</ul>

|  ?- write(hello).  % hello is a constant */

|  ?- write(Hello).  % Hello is a variable. Its address will be displayed*/

|  ?- write(‘hello world’). % a string is printed */

| ?- read(Y), write(‘The variable entered is ‘), write(Y), nl. /* nl prints a newline. Type a period and an enter at the end of the input */ |  ?- X is 2+2.

|  ?- Y is 5*8.

|  ?- Y is 2**10.

|  ?- length([a, b, x, y, 2, 45, z], L).

|  ?- append([a, b, c, d], [4, 6, 8], LL).

|  ?- append(X,Y,[a,b,c]). Then, type “;” to obtain all possible answers.

|  ?- X is [1 | [2 | [3 | []]]], write(X). Explain the output. 6 Use trace and notrace before and after your questions in Question 5. For example

|?- trace. |  ?- X is [1 | [2 | [3 | []]]], write(X). Explain the output.

|?- notrace.




<strong> </strong>Programming Assignment

<ol>

 <li>Using Scheme higher-order function map to implement the string encryption and decrption.</li>

</ol>

Make a file called encrypt.rkt for this question.                                                        [10 points]

<ul>

 <li>The encryption function must (1) take the encryption key (key can be between 1 and 4) from the keyboard using (read); and (2) encrypt alphabetic characters and digits only. [5]</li>

 <li>The decryption function must (1) take the encryption key from the keyboard using (read) and (2) decrypt the string generated from your encryption function. [5]</li>

</ul>

Test cases:

(encrypt “Hello CSE240!”)

(decrypt “Khoor FVH573!”)

3

“Khoor FVH573!”

3

“Hello CSE240!”

Note: When you encrypt a valid character (letters and digits), you add a key to the character.

When you decrypt, you will have a different set of the valid characters, which is caused by +key. You can limit the allowed key value to be 1, 2, 3, and 4.

<ol start="2">

 <li>Consider the following diagram of a family tree: [25 points]</li>

</ol>

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/05/218.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/05/218.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>

<table width="0">

 <tbody>

  <tr>

   <td width="590">/* Database for family tree. It consists of facts and rules. */ /* A portion of the family tree has been implemented for you *//* Facts */ male(kam). male(rob). female(ana). female(syd).father_of(kam, rob). /* kam is the father of rob */ father_of(kam, syd). /* kam is the father of syd */ mother_of(ana, rob). /* ana is the mother of rob */ mother_of(ana, syd). /* ana is the mother of syd */ /* Rules */ is_male(X) :-   male(X);        father_of(X, _).</td>

  </tr>

 </tbody>

</table>

Enter the program using a text editor, such as nano or pico, under Unix operation system and save the file as <sub>family_tree.pl</sub>. You may enter the program on your own computer using a simple editor, such as Notepad, and upload the program into your cse240prolog directory in <em>general</em> server.

Compile the program using the Prolog command:

&gt; gplc family_tree.pl

Enter GNU Prolog programming environment by executing the Unix command <sub>gprolog</sub>.

Execute the program <sub>family_tree</sub> by typing GNU Prolog command

|?- [family_tree].

To exit from GNU Prolog, type your end-of-file character at the main Prolog prompt  ^d (Ctrl-d).

| ?- ^d

Ask questions by typing, e.g.:

|?- father_of(kam, rob).

|?- mother_of(ana, syd).

Please read Textbook Appendix B.4 Prolog Tutorial for more detail. You can also find a complete set of GNU Prolog commands at http://www.gprolog.org/manual/gprolog.html.

Now, you can start to add your code into the program.

2.1 Complete the program by adding facts and rules for the remaining members on the family tree. A portion has already been completed for you above for clarification. Please pay close attention when adding the remaining famiy members. All letters should be lowercase. [5]

<em>For all of the following questions, please label them. For example, if Question 1.0 asks you to define a rule called is_male (X) that returns “yes” (or “true”) if X is the father of a member of the family, then your code should look like: </em>




/* Question 1.0 */ is_male(X) :-

male(X);          father_of(X, _).




2.2 Define (add into the database) a rule called is_female(X) that returns “yes” (or “true”) if X is a female or the mother of a member of the family.  [3]

Note: the system will return a “yes”, if it finds a “true” answer and there exist no more true answers. The system will return “true ?” if it finds a “true” answer and there are still possibly further matches. In this case, if you type “enter”, it will return “yes” and stop. If you type “;”, it will continue to search for further answers.

2.3        Define a rule called parent_of(X, Y) that returns “yes” (or “true”) if X is a parent of Y. [3]

2.4       Define a rule called sibling_of(X, Y) that returns “yes” (or “true”) if X is a sibling of Y. [3]

2.5 Define one rule called grandmother_of(X, Z) that returns “yes” (or “true”) if X is a grandmother of Z and one rule called grandfather_of(X, Z) that returns “yes” (or “true”) if

X is a grandfather of Z.                                                                                                          [3]

2.6 Define a rule called descendent_of(X, Y) that returns “yes” (or “true”) if X is a descendent of Y. Note: you will need to use recursion as well as the parent rule defined above. [3]

2.7 Define and add a rule into the database: familyquestions. The question tests all the rules that you have added in the database in the previous questions. Use AND “,” to connect the subquestions and make sure that all your subquestions have a true answer. Add “write” statements to print the information.        [5]




<ul>

 <li>Consider the following database that will be used to determine meals for halloween and thanksgiving with the ingredients needed for the given sides. Make a file called meals.pl for this question</li>

</ul>

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/05/674-1.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/05/674-1.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>

<ul>

 <li>Create facts for the entres: entre(X, Y) where X is the occasion and Y is the entre.</li>

</ul>

Create facts for the side: side(X, Y) where X is the occasion and Y is the side.

Create facts for the ingredients : ingredient(X, Y) where X is the side and Y is the ingredient.

[4]

<ul>

 <li>Create a rule meal(X, Y) where X is the occasion and Y is the food that will be served.           For example, meal(thanksgiving, X) should return turkey, bread, and pumpkinpie.     [3]</li>

</ul>

Hint: There could be different solutions. One of the possible solution is to define helper rule such as: food(X, E, S) :- entre(X, E), side(X, S). Then, you can use the food rule in your meal rule as a condition. You can use a few write clauses to print the values in the variables E and S.

<ul>

 <li>Create a rule shoppinglist(X, Y) where X is the occasion and Y is the ingredient needed.</li>

</ul>

For example, shoppinglist(thanksgiving, X) should return egg, flour, pumpkin,  and pie. [3]

<ul>

 <li>Define and add a rule into the database: mealquestions. The question tests all the rules that you have added in the database in the previous questions. Use AND “,” to connect the subquestions and make sure that all your subquestions have a true answer. Add “write”</li>

</ul>

statements to print the information.                                                                                       [5]


