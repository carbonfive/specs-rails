# Strategies for writing specs
## For a Rails App
---
This document outlines different spec'ing strategies that can be considered for different situations.

First, lets point out the common techniques (best practices) for writing specs.

Combining these techniques in various ways, and in varying degrees, will yield different strategies.
---

## Spec Techniques

### Feature Specs
	* Definition:
	  specs that define what user experience is provided by a feature
	* Tech:
	  Capybara
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
	* example: (requires test_response_data.rb spec helper)
      require 'spec_helper'

      describe "Natural Search" do
        context "given different levels of profile completeness" do
          let!(:empty_thing)    {create :thing}
          let!(:partial_thing)  {create :partial_thing}
          let!(:complete_thing) {create :complete_thing}
          let (:expected_order) {[ complete_thing, partial_thing, empty_thing] }

          it 'returns the most complete things first' do
            get search_path
            thing_ids = response.data_for('thing-id')
            expect(thing_ids.length).to eq 3
            expect(thing_ids).to eq expected_order.map {|u| u.id.to_s}
          end
        end
      end
[how to write a request specs for a web app]()
[how to write a request specs for an api]()

### View Specs /app/views
	* Definition:
	  Design how data is rendered to a User
	* Technique:
	* Pressure Points to Focus on:
	* Current Conventions:
	* example:
	  todo
[how to write a view spec]()

### Controller Specs /app/controllers
	* Intention:
	  Design each of the incomming requests to your your app
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
	  Design the public interfaces of your Domain Model classes (or single purpose classes)
	* Watch:
	  [how to write a model spec](http://www.confreaks.com/videos/2452-railsconf2013-the-magic-tricks-of-testing)
	* Technique: 
	  Isolate the model from other objects
	  For ActiveRecord models: use build instead of create to setup your tests where possible
	* Pressure Points to Focus on:
	  write expectations for messages sent to a public class methods
	  write expectations for messages sent to public instance methods
	  write expectations for outgoing commands
	  No need to write expectations for private methods
	* Current Conventions:
	  describe '#instance_method' do
	  describe '.class_method' do

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
