# Rspec Core

Rspec is an automated testing framework for Ruby, designed for use in Behaviour
Driven Development and Test Driven Development.

rspec-core includes the Rspec runner, output formatters, and the `rspec`
command.

## Install

    [sudo] gem install rspec --prerelease

This will install the rspec, rspec-core, rspec-expectations and rspec-mocks
gems.

## Get Started

Start with a simple example of behavior you expect from your system. Do
this before you write any code:

    # in spec/calculator_spec.rb
    describe Calculator, "add" do
      it "returns the sum of its arguments" do
        Calculator.new.add(1, 2).should eq(3)
      end
    end

Run this with the rspec command, and watch it fail:

    $ rspec spec/calculator_spec.rb
    ./spec/calculator_spec.rb:1: uninitialized constant Calculator

Implement the simplest solution:

    # in lib/calculator.rb
    class Calculator
      def add(a,b)
        a + b
      end
    end

Be sure to require the implementation file in the spec:

    # in spec/calculator_spec.rb
    # - Rspec adds ./lib to the $LOAD_PATH, so you can
    #   just require "calculator" directly
    require "calculator"

Now run the spec again, and watch it pass:
    
    $ rspec spec/calculator_spec.rb
    .

    Finished in 0.000315 seconds
    1 example, 0 failures

Use the documentation formatter to see the resulting spec:

    $ rspec spec/calculator_spec.rb --format doc
    Calculator add
      returns the sum of its arguments

    Finished in 0.000379 seconds
    1 example, 0 failures

#### Also see

* [http://github.com/rspec/rspec](http://github.com/rspec/rspec)
* [http://github.com/rspec/rspec-expectations](http://github.com/rspec/rspec-expectations)
* [http://github.com/rspec/rspec-mocks](http://github.com/rspec/rspec-mocks)
* [http://github.com/rspec/rspec-dev](http://github.com/rspec/rspec-dev)

