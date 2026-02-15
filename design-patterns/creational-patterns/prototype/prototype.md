# Prototype


![prototype](../../../images/creational-patterns/prototype/introduction.png)

## Intent

Lets you copy existing objects without making the code dependent on their classes.

## Problem

Sometimes objects can't be copied by making a new object of the same class (with all the fields) because some of the fields are private.

## Solution

Delegates cloning to actual objects being cloned, using a `clone` method.

`clone` method: creates an object of the current class and all the fields into the new one.