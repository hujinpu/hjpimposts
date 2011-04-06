The ruby String class is optimized for the data processing side of strings while symbols are meant to take over the “stands for” role.

there can only ever be one instance of any given symbol:

--- Ruby
a = :all
b = a
c = :all
# True! All true!
puts a == c
puts a === c
puts a.eql?(c)
puts a.equal?(c)
---

**symbols are immutable**

 Inside of Hash there is special case code that makes a copy of any keys passed in if the keys happen to be strings. So, please use symbols directly.

in Ruby 1.9 public_methods does indeed return an array of symbols

"gems/bundler-1.0.10/lib/bundler/vendor/thor/core_ext/hash_with_indifferent_access.rb" allows you to mix and match strings and symbols with cheerful abandon.
