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

This structural design is based on the workflow engine, it requires an object based approach to programming.
Each object should at a minimum the ICyclic interface, this is found in the base library.

The runner calls the cyclic method of all registered modules.

## Description

The Runner class is meant to form the background of the PLC program, at a minimum you will require the addComponent and cycle methods. Your module should be registered with the runner once, it will reject registering the same module multiple times. This fits with a machine initialisation operation. Next call the cycle method, all registered modules will be called.
It is important to call the initialise method at least once as the cyclic method will reject running until the modules are initialised, if empty the initiliase flag will just be set true.

The runner also supports an initialisation, implementing the I_Initialse interface means when the object is registered it is checked for this interface. If its found then you can split the runner calls. Using the initialise to call any initialse method of all registered objects, check all repsond as initialised, before calling the cycle method for the first time.

You are able to remove a module using the removemodule method, this will remove the module refernece and so block it being called, you can also clear to remove all registered modules.

Looking into the testing library will show how the runner can be used.

## Repository Design

This repo is split into 2 projects, the library containing the runner and a unit tesitng library.
Utilising reference libraries you can run them, you can run in UmRT.


## Tests

The library is referenced in the test project, unit testing is done in TwinCAT, which requirs a TC target device.
User Mode RunTime (UmRT) can support this.

## Support

LOL, little old me now, all by myself :-)


## Requirements: 

Please include important requirements in the local readme files.

Currently nothing more than:

TwinCAT 4026


## Document List





