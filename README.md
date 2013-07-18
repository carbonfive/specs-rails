# Strategies for writing specs
## For a Rails App
---
This document outlines different spec'ing strategies that can be considered for different situations.

First, lets point out the common techniques (best practices) for writing specs.

Combining these techniques in various ways, and in varying degrees, will yield different strategies.

---

## Spec Techniques

### User Experience Specs
	* Definition:
	  specs that define what user experience is being provided
	* Technique:
	* Pressure Points to Focus on:
	* Current Conventions:
	* example:
	  todo (Use request specs with capybara?)
[how to write a user experience spec]()

### Request Specs /app/controllers 
	* Definition:
	  specs for an ApplicationController
	* Technique:
	* Pressure Points to Focus on:
	* Current Conventions:
	* example:
	  todo
[how to write a request specs for a web app]()
[how to write a request specs for an api]()

### View Specs /app/views 
	* Definition:
	  specs for views that get rendered
	* Technique:
	* Pressure Points to Focus on:
	* Current Conventions:
	* example:
	  todo
[how to write a view spec]()

### Controller Specs /app/controllers 
	* Definition:
	  specs for an ApplicationController
	* Technique:
	  Isolate the controller
	  Provide doubles for models and services.
	  No view is rendered either.
	* Pressure Points to Focus on:
	* Current Conventions:
	* example:
	  todo
[how to write a controller spec]()

### Model Specs: /app/models
	* Definition:
	  Specs for an individual domain Model
	* Technique: Isolate the model from other objects, except allow it to persist to a DB
	* Pressure Points to Focus on:
	  write a spec for messages to the public class methods you write
	  write a spec for messages to the public instance methods you write
	  write a spec for outgoing commands
	* Current Conventions:
	  describe '#instance_method' do
	  describe '.class_method' do
	* example:
	  todo
[how to write a model spec](http://www.confreaks.com/videos/2452-railsconf2013-the-magic-tricks-of-testing)

### Ambiguous Terms
The following terms mean different things to different people and won't be used in this document:

    Unit Test
    Functional Test
    Integration Test
    Acceptance Test

## The Strategies
We can combine the of the above Spec Techniques

### Developing an API

### Developing a Lean MVAP

### Developing a Personal WebApp

### Developing an Enterprise App
