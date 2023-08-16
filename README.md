# Exploring Algorithms to convert from Infix to Postfix Notation (Data Structures & Algorithms Course Project)

## About Infix, Prefix and Postfix Notations
*Infix* notation is a way of writing mathematical expressions in which the operators are placed between the operands. For example, the expression "3 + 4" is written in infix notation, where "+" is the operator and "3" and "4" are the operands. In infix notation, the order of operations is determined by operator precedence and parentheses. For example, multiplication and division are typically performed before addition and subtraction, unless parentheses are used to indicate a different order of operations.

In *prefix* notation, also known as Polish notation, the operator comes before the operands. This format eliminates the need for parentheses and has a fixed order of operations, making it easier to parse and evaluate expressions. However, it can be hard to read for complex expressions. 

*Reverse Polish notation (RPN)*, also known as **Reverse Łukasiewicz notation**, is a way of writing mathematical expressions in which the operators come after the operands. For example, the infix expression "3 + 4" would be wriƩen in postfix notation as "3 4 +". In *postfix* notation, the order of operations is determined solely by the order of the operands and operators. The first operand encountered is used with the first operator encountered, and so on. 

For example, the postfix expression "3 4 + 5 *" is evaluated as follows: 
- Push 3 onto the stack. 
- Push 4 onto the stack. 
- Pop 4 and 3 from the stack, add them, and push the result (7) onto the stack. 
- Push 5 onto the stack. 
- Pop 5 and 7 from the stack, multiply them, and push the result (35) onto the stack. 
- The result is 35. 

Postfix notation is commonly used in computer programming, particularly in stack-based programming languages such as Forth and PostScript.It is also used in some calculators, where it can simplify the process of evaluating complex expressions.

Infix and postfix notations have their own advantages and disadvantages, and which one is better depends on the context and the specific use case. Infix notation is more familiar and intuitive to most people, as it closely resembles the way we write and speak mathematical expressions. It also allows for the use of parentheses to specify the order of operations, which can make complex expressions easier to read and understand. 

On the other hand, postfix notation can be easier to parse and evaluate algorithmically, particularly in computer programming. This is because postfix notation does not require the use of parentheses or operator precedence rules, and the order of operations can be determined simply by iterating over the operands and operators in order.

## Historical Importance: 

Hewlett-Packard (HP) engineers were among the first to design and produce calculators that used Reverse Polish Notation (RPN) as their primary input method. The first HP calculator to use RPN was the HP-9100A, which was introduced in 1968. RPN was chosen as the input method for HP calculators because it provided a more efficient and natural way of entering and evaluating mathematical expressions. With RPN, the user would enter the operands first, followed by the operator. For example, to add 2 and 3, the user would enter "2 [enter] 3 +". HP calculators that used RPN became very popular among engineers, scientists, and other professionals who needed to perform complex calculations quickly and efficiently. 

Today, RPN calculators are still used by many professionals and enthusiasts who appreciate their efficiency and ease of use. 

## Current Relevancy: 

Stack-oriented programming languages such as Forth, Factor, and PostScript are some of the current implementations that use Reverse Polish Notation (RPN) as their primary input and evaluation method. The UNIX system calculator program "dc" (desktop calculator) also uses postfix notation as its primary input method. Postfix notation is often preferred in calculators and other mathematical tools because it eliminates the need for parentheses and operator precedence rules, which can make complex expressions easier to enter and evaluate. It also allows for easy manipulation of the stack of operands, which can simplify the process of performing iterative or recursive calculations.

# Algorithms Explored:

1. **Manually Converting Infix to Postfix [Parenthesizing Infix]**

The first thing you need to do is to fully parenthesize the expression. So, the expression ```(3+6) *(2-4) +7 becomes (((3 + 6) * (2 - 4)) + 7)``` 
Now, move each of the operators immediately to the right of their respective right parentheses. 
```(((3 + 6) * (2 - 4)) + 7) becomes 3 6 + 2 4 - * 7 + ```

As you see this can be computationally expensive since “parenthesizing” the expression is not feasible for longer expressions and hence becomes inefficient. 

2. **Single Stack-based algorithm to convert from Infix to Postfix expression [The Shunting-Yard Algorithm]**

**Algorithm**:

- Define a function precedence that assigns a numerical value to each operator, based on its precedence level. 
- Define a function infixToPostfix that takes an infix expression as input and returns the equivalent postfix expression as output.
- Initialize an empty string called result to store the postfix expression, and a stack called operators to store the operators. 
- Iterate through each character of the input infix expression, and for each character, perform one of the following actions:
    - If the character is an operand (a leƩer or a digit), append it to the result string. 
    - If the character is an opening parenthesis, push it onto the operators stack. 
    - If the character is a closing parenthesis, pop operators from the operators stack and append them to the result string until an opening parenthesis is found. Then pop the opening parenthesis from the operators stack.
    - If the character is an operator, pop operators from the operators stack and append them to the result string as long as the operator at the top of the stack has equal or higher precedence than the current operator. Then push the current operator onto the operators stack.
- After iterating through all characters of the input expression, pop any remaining operators from the operators stack and append them to the result string.
- Return the result string as the equivalent postfix expression.

3. **Conversion from Infix to Postfix without Stacks**

4. **Conversion from infix to Postfix using Stacks & Queues**

5. **Recursive Descent Parsing**
- Recursive descent parsing is a type of top-down parsing algorithm used to analyze the syntactic structure of a program or expression, particularly in computer programming languages. It is a widely used technique for building parsers for programming languages and other formal grammars. 

# Link to Repository containing RPN Calculator Implementation

https://github.com/AnuragBambardekar/RPN-Calculator