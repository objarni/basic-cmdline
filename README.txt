Basic command line argument parser
==================================

We want a library to help us write simple C code for parsing command line
arguments in our applications.

Only one style of arguments are supported, on the form "--flag argument", e.g.

   our_app --script file1.script

In this example, "script" is the key, and "file1.script" is the value.

It should be easy to determine that the parsing failed for some reason, so that
the application can write out a helpful usage text.

The parser only needs to handle up to 3 of these key-value pairs, so this is an
example of using all three arguments:

  our_app --script file1.script --log log.txt --verbosity high

It is also of high value to be able to create a formatted help-text that the
application can use when parsing fails; for the above 3 arguments, the help text
could be something like this:

   --script <script>              A script file to interpret by application
   --log <log>                    What file to log (Defaults to "log.txt")
   --verbosity <verbosity>        How verbose output to log into log file Can be
                                  one of low, moderate, high

Note: the interpretation of what the command line options mean in the
application is entirely up to the app using this library to do, so the help
texts to the right needs to be passed to the library from the app so the library
will be able to come up with the help text.

There is a popular single-letter forms of arguments, and this library does not
need to handle such; neither does "--flag=arg" style argument passing need to be
supported - but you are free to implement any as an extra exercise!

E.g these examples are 'nice to have' but not required:

  -s file1.script
  -s=file1.script
