Basic command line argument parser
==================================

We want a library to help us write simple C code for parsing command line
arguments in our applications.

Must have
---------
Only one style of arguments are supported, on the form "--flag argument", e.g.

   our_app --script file1.script

In this example, "script" is the key, and "file1.script" is the value.

It should be easy to determine that the parsing failed for some reason, so that
the application can write out a helpful usage text instead. Using single dash
like "-script" is an example of incorrect use.

The parser only needs to handle up to 5 of these key-value pairs, so this is an
example of using all five arguments 'slots':

  our_app --log a.og --verbose high --script a.s --debug true --format json

Any other argument or formatting does not parse, and should be easy to handle
for the application.

Nice to have
------------
There is a popular single-letter forms of arguments, and this library does not
need to handle such; neither does "--flag=arg" style argument passing need to be
supported - but you are free to implement any as an extra exercise!

E.g these examples are 'nice to have' but not required:

  -s file1.script
  -s=file1.script
