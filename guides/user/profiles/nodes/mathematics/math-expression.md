---
title: Math Expression Node
description: The help page for the math expression node
published: true
date: 2022-10-04T21:10:34.617Z
tags: 
editor: markdown
dateCreated: 2022-10-04T21:03:40.768Z
---

# Introduction
The math node is an advanced node that allows you to write your own math expressions.  
You can use this node for all kinds of mathematical use-cases even some also covered by other nodes.

The power of the node lies in the fact that each input pin is available as a variable in the expression.

![math-expression.png](/profiles/nodes/mathematics/math-expression.png){.elevation-3 .radius-3}

> Internally the node uses the [NoStringEvaluating](https://github.com/KovtunV/NoStringEvaluating) library by [KovtunV](https://github.com/KovtunV).
{.is-info}


# Pins
The math node exclusively offers numeric inputs and outputs.
#### Input
The node has an input pin collection, each input pin is available inside the expression using it's corresponding letter.
#### Output
The node has a single output pin containing the result of the math expression.

# Math functions
The math node offers a wide variety of functions listed below.
> Source: https://github.com/KovtunV/NoStringEvaluating/blob/master/README.md
{.is-info}


### Precompiled variables

There are some known variables, you shouldn't send them to Calc method.

| Key word | Description                                                     | Value                   |
| -------- | --------------------------------------------------------------- | ----------------------- |
| pi       | Pi, Archimedes' constant or Ludolph's number                    | 3.14159265358979323846  |
| tau      | A circle constant equal to 2π                                   | 6.283185307179586476925 |
| e        | Napier's constant, or Euler's number, base of Natural logarithm | 2.7182818284590452354   |
| true     | Boolean True                                                    | True                    |
| false    | Boolean False                                                   | False                   |
| ASC      | Boolean True                                                    | True                    |
| DESC     | Boolean False                                                   | False                   |

These variables are register independent, you can write Pi, [PI], pI, True, etc...

## Operators

| Key word | Description    | Example |
| -------- | -------------- | ------- |
| +        | Addition       | a + b   |
| -        | Subtraction    | a - b   |
| \*       | Multiplication | a \* b  |
| /        | Division       | a / b   |
| ^        | Exponentiation | a^b     |

## Boolean operators

| Key word | Description               | Example    |
| -------- | ------------------------- | ---------- |
| <        | Lower than                | a < b      |
| <=       | Lower or equal            | a <= b     |
| >        | Greater than              | a > b      |
| >=       | Greater or equal          | a >= b     |
| ==       | Equality                  | a == b     |
| =        | Equality                  | a = b      |
| !=       | Inequation                | a != b     |
| <>       | Inequation                | a <> b     |
| &&       | Logical conjunction (AND) | a && b     |
| \|\|     | Logical disjunction (OR)  | a \|\| b   |
| !        | Negation                  | !IsNull(a) |

## Functions

### Math

| Key word | Description                                            | Example                                         |
| -------- | ------------------------------------------------------ | ----------------------------------------------- |
| add      | Summation operator                                     | add(a1; a2; ...; an) can include List<double>   |
| multi    | Multiplication                                         | multi(a1; a2; ...; an) can include List<double> |
| mean     | Mean / average value                                   | mean(a1; a2; ...; an) can include List<double>  |
| min      | Minimum function                                       | min(a; b) can include List<double>              |
| max      | Maximum function                                       | max(a; b) can include List<double>              |
| Rpund    | Rounds the designated number to the specified decimals | Round(a; decimals)                              |
| ln       | Natural logarithm function (base e)                    | ln(x)                                           |
| log      | Logarithm function (base b)                            | log(a; b)                                       |
| log2     | Binary logarithm function (base 2)                     | log2(x)                                         |
| log10    | Common logarithm function (base 10)                    | log10(x)                                        |
| sqrt     | Squre root function                                    | sqrt(x)                                         |
| abs      | Absolut value function                                 | abs(x)                                          |
| sgn      | Signum function                                        | sgn(x)                                          |
| sign     | Signum function                                        | sign(x)                                         |
| floor    | Floor function                                         | floor(x)                                        |
| ceil     | Ceiling function                                       | ceil(x)                                         |
| mod      | Modulo function                                        | mod(a; b)                                       |
| fact     | Factorial function                                     | fact(x)                                         |
| fib      | Fibonacci number                                       | fib(x)                                          |
| gcd      | Greatest common divisor                                | gcd(a1; a2; ...; an)                            |
| lcm      | Least common multiple                                  | lcm(a1; a2; ...; an)                            |

### Trigonometry

| Key word | Description                              | Example     |
| -------- | ---------------------------------------- | ----------- |
| sin      | Trigonometric sine function              | sin(x)      |
| cos      | Trigonometric cosine function            | cos(x)      |
| tg       | Trigonometric tangent function           | tg(x)       |
| tan      | Trigonometric tangent function           | tan(x)      |
| ctg      | Trigonometric cotangent function         | ctg(x)      |
| cot      | Trigonometric cotangent function         | cot(x)      |
| ctan     | Trigonometric cotangent function         | ctan(x)     |
| sec      | Trigonometric secant function            | sec(x)      |
| csc      | Trigonometric cosecant function          | csc(x)      |
| cosec    | Trigonometric cosecant function          | cosec(x)    |
| asin     | Inverse trigonometric sine function      | asin(x)     |
| arsin    | Inverse trigonometric sine function      | arsin(x)    |
| arcsin   | Inverse trigonometric sine function      | arcsin(x)   |
| acos     | Inverse trigonometric cosine function    | acos(x)     |
| arcos    | Inverse trigonometric cosine function    | arcos(x)    |
| arccos   | Inverse trigonometric cosine function    | arccos(x)   |
| atg      | Inverse trigonometric tangent function   | atg(x)      |
| atan     | Inverse trigonometric tangent function   | atan(x)     |
| arctg    | Inverse trigonometric tangent function   | arctg(x)    |
| arctan   | Inverse trigonometric tangent function   | arctan(x)   |
| actg     | Inverse trigonometric cotangent function | actg(x)     |
| acot     | Inverse trigonometric cotangent function | acot(x)     |
| actan    | Inverse trigonometric cotangent function | actan(x)    |
| arcctg   | Inverse trigonometric cotangent function | arcctg(x)   |
| arccot   | Inverse trigonometric cotangent function | arccot(x)   |
| arcctan  | Inverse trigonometric cotangent function | arcctan(x)  |
| sinh     | Hyperbolic sine function                 | sinh(x)     |
| cosh     | Hyperbolic cosine function               | cosh(x)     |
| tgh      | Hyperbolic tangent function              | tgh(x)      |
| tanh     | Hyperbolic tangent function              | tanh(x)     |
| coth     | Hyperbolic cotangent function            | coth(x)     |
| ctgh     | Hyperbolic cotangent function            | ctgh(x)     |
| ctanh    | Hyperbolic cotangent function            | ctanh(x)    |
| sech     | Hyperbolic secant function               | sech(x)     |
| csch     | Hyperbolic cosecant function             | csch(x)     |
| cosech   | Hyperbolic cosecant function             | cosech(x)   |
| arcsec   | Inverse trigonometric secant             | arcsec(x)   |
| asinh    | Inverse hyperbolic sine function         | asinh(x)    |
| arsinh   | Inverse hyperbolic sine function         | arsinh(x)   |
| arcsinh  | Inverse hyperbolic sine function         | arcsinh(x)  |
| acosh    | Inverse hyperbolic cosine function       | acosh(x)    |
| arcosh   | Inverse hyperbolic cosine function       | arcosh(x)   |
| arccosh  | Inverse hyperbolic cosine function       | arccosh(x)  |
| atgh     | Inverse hyperbolic tangent function      | atgh(x)     |
| atanh    | Inverse hyperbolic tangent function      | atanh(x)    |
| arctgh   | Inverse hyperbolic tangent function      | arctgh(x)   |
| arctanh  | Inverse hyperbolic tangent function      | arctanh(x)  |
| acoth    | Inverse hyperbolic cotangent function    | acoth(x)    |
| actgh    | Inverse hyperbolic cotangent function    | actgh(x)    |
| actanh   | Inverse hyperbolic cotangent function    | actanh(x)   |
| arccoth  | Inverse hyperbolic cotangent function    | arccoth(x)  |
| arcctgh  | Inverse hyperbolic cotangent function    | arcctgh(x)  |
| arcctanh | Inverse hyperbolic cotangent function    | arcctanh(x) |
| asech    | Inverse hyperbolic secant function       | asech(x)    |
| arsech   | Inverse hyperbolic secant function       | arsech(x)   |
| arcsech  | Inverse hyperbolic secant function       | arcsech(x)  |
| acsch    | Inverse hyperbolic cosecant function     | acsch(x)    |
| arcsch   | Inverse hyperbolic cosecant function     | arcsch(x)   |
| arccsch  | Inverse hyperbolic cosecant function     | arccsch(x)  |
| acosech  | Inverse hyperbolic cosecant function     | acosech(x)  |
| arcosech | Inverse hyperbolic cosecant function     | arcosech(x) |
| rad      | Degrees to radians function              | rad(x)      |
| deg      | Radians to degrees function              | deg(x)      |
| exp      | Exponential function                     | exp(x)      |

### Logic

| Key word | Description                                              | Example                                                  |
| -------- | -------------------------------------------------------- | -------------------------------------------------------- |
| if       | If function                                              | if(cond; expr-if-true; expr-if-false)                    |
| iff      | If function                                              | iff( cond-1; expr-1; ... ; cond-n; expr-n )              |
| and      | Logical conjunction (AND)                                | and(a1; a2; ...; an)                                     |
| or       | Logical disjunction (OR)                                 | or(a1; a2; ...; an)                                      |
| not      | Negation function                                        | not(x)                                                   |
| IsNaN    | Returns true if value is a Not-a-Number (NaN)            | isNaN(x)                                                 |
| IsError  | Returns true if this is a double.NaN                     | IsError(ToNumber('Text'))                                |
| IsMember | Checks if second argument is a member of list from first | IsMember({'printer', 'computer', 'monitor'}; 'computer') |
| IsNumber | Returns true if this is a number                         | IsNumber(256)                                            |
