Basic command line argument parser
==================================

We want a library to help us write simple C code for parsing command line arguments in our applications.

Only one style of arguments are supported, on the form "--flag argument", e.g.

   our_app --script file1.script

In this example, "script" is the key, and "file1.script" is the value.

The parser only needs to handle up to 3 of these key-value pairs, so this is an example of using all three
arguments:

  our_app --script file1.script --log log.txt --verbosity high

There is a popular single-letter forms of arguments, and this library does not need to handle such; neither
does = style argument passing have to be supported - but you are free to implement any as an extra exercise!

E.g this examples that are 'nive to have' but not required to support:

  -s=file1.script   # this form is a bonus or nice to have, not a requirement!

However, it should be easy to determine that the parsing failed for some reason.

It is also required to be able to create a formatted help-text that the application can use when parsing failed.

For the above 3 arguments, the help text could be something like this:

   --script <script>              Specifies a script file to be used by application.
   --log <log>                    What file to log into.
   --verbosity <verbosity>        How verbose output to log into log file. One of low|high


Note: the interpretation of the command line options is entirely up to the app using this library to do, so this
help text is something that the library needs from the app to be able to come up with the help text.
