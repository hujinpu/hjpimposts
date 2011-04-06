Arbitrarily quoted strings always start with a percent sign (%) followed by the letter q. The character after the q is the actual string delimiter—we used a brace ({) in the example above. If your delimiter has a natural partner, the way } goes with {, then that’s the character you use to close the string. In the example above we could have used ( and ) instead of { and }

--- Ruby
%q{ your string } === ' your string '
%Q{ your string } === " your string "
---

some powerful string method:

+ lstrip, rstrip, strip
+ chmop (Note that chomp only does one newline at a time)
+ chop
+ swapcase
+ sub, gsub
+ split
+ index
+ each_char, each_byte, each_line

**Ruby strings are mutable**

So get in the habit of saying this:

--- Ruby
first_name = first_name.upcase
---

Instead of this:

--- Ruby
first_name.upcase!
---
