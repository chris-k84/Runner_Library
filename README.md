# Runner Library

## Contents

1. [Motivation](#motivation)
2. [The Goal](#the-goal)
3. [Background](#background)
4. [Description](#description)
3. [Repository Design](#repository-design)
4. [Tests](#Tests)
5. [Support](#Support)
6. [Requirements](#Requirements)
7. [Documents](#Document-List)

## Motivation

This started out as an XTS library, then became something else, a huge crawling repo with too much stuff doing too many things. So it's been broken up into numerous libraries which will break out the elements into modules which align in function and intent. Basically the motivation is to have a clue whats going on :-) 

## The Goal

The goal of this repo is to build on the base repo, using the cyclic modules to create an object specifically to run a modular system. This module will call all the cyclic logic of all registered objects and handle initialisation.

## Background

The background to this is long and complicated but basically revolves around a series of conversations, though experiments and trial and error projects. 
Essentially there are lots of ways of setting up a PLC project, the idea behind a runner is to provide a flat structure for your program. Often you have a heiracicl structure with many levels, when this happens knowing when something executes becomes diffcult.
The runner provides a flat execution, all cyclic operations are called one after another, not based on the object composition, but simply on an arbitrary order.
This order is typically the order the modules are added to the runner.   

## Description


## Repository Design



## Tests



## Support

LOL, little old me now, all by myself :-)


## Requirements: 

Please include important requirements in the local readme files.

Currently nothing more than:

TwinCAT 4026


## Document List





