# Builder


![builder](../../../images/creational-patterns/builder/introduction.png)

## Intent

Lets you produce different types & representations of an object using the same construction code. 

## Problem

You want a way to extend the base class and create subclasses to cover all combinations of the parameters.

## Solution

Extract the object construction code out of its own class & move it to separate objects called builders.

Director class: defines the order to execute the building steps in.