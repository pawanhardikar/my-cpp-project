# Build a CPP project using Jenkins shared library

## Jenkinsfile configuration

- consume shared library using `@Library("my-shared-library@0.1.0")` Here **my-shared-library** is the name of the shared library that is being used and **@0.1.0** is the tag or the version of the my-shared-library that will be used.


cppBuild() # This will call the call() function in cppBuild.groovy as **call()** is the default function in groovy. Keep in mind here **cppBuild** is the name of the groovy file and not any function in the groovy file

## What are closures? Why is it used
- It is an anonymous block of code that can be passed around and executed later.
- The body closure is assigned a delegate (body.delegate = this), which allows it to access properties of the surrounding object.
- Later, inside the node block, the script calls body() at the end, executing the closure that was passed into the function.
- So in short we use closures for easy customization because they allow flexible execution.

## How to call other functions from the shared library

- Syntax: cppBuild.function_name() Here function_name() can be any function present in the groovy file and while calling make sure that if any of the arguements has to be passed, usually there will be default values set if no values are passed as arguements during the function call.