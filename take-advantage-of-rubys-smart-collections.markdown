If you need to initialize an array of strings, where none of the strings have embedded spaces, you can simply say:

`poem_words = %w{ twinkle little star how I wonder }`

If you doesn't care about the types of the hash keys, you can simply do:

`book_info = { first_name: 'Russ', last_name: 'Olsen' }`

Sometimes, however, what you need is a method that will take a completely arbitrary set of arguments(like javascript function). Ruby has a special syntax for this: If, in your method definition, you stick an asterisk before one of your parameter names, that parameter will soak up any extra arguments passed to the method as a array(like arguments in javascript).

    def test_fun(*args)
      args.each {|el| puts el}
    end

    test_fun('one', 'two', 'three')

If the hash is at the end4 of the argument list, we can leave the braces off when we call the method.

    def load_font(spec)
      puts spec.keys
    end

    load_font :name => 'times roman', :size => 12

map, each, inject method are extensive toolkit, a key part of knowing how to program in Ruby is getting to go through [Array](http://www.ruby-doc.org/core/classes/Array.html) and [Hash](http://www.ruby-doc.org/core/classes/Hash.html) api documents.

**Anyway, be sure you know what a method is going to do to your collection before you call it.**

Ruby arrays and hashes have one thing in common that takes many programmers by surprise: They are both ordered. (With the advent of Ruby 1.9, however, hashes have become firmly ordered.)

require 'pp'
hey_its_ordered = { first: 'mama', second: 'papa', third: 'baby' }
hey_its_ordered.each { |entry| pp entry }
puts
hey_its_ordered[:first] = 'mam'
hey_its_ordered.each { |entry| pp entry }

What we really need is a collection that doesn’t allow duplicates but does feature very fast and easy answers to the “is this object in there?” question. The punch line is that we need a set.

    require 'set'
    word_set = Set.new(%w{one two three two one three four})
    pp word_set
