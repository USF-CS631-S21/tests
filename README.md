# tests
Project and lab tests for autograding

# Instructions

To use the autograder you will need to do some setup first. The good news is that once you get things set up, you will just pull new tests (and maybe updates to the autograder) as needed throughout the semester.

You will first clone this repository. In contains the tests for the projects and labs. It will be updated with tests for new projects and labs throughout the semester. You might consider putting it in: 

```
~/cs631
```

So, after you clone, you should have:

```
~/cs631/tests
```

You will need to clone the autograder repo here:

https://github.com/phpeterson-usf/autograder

This requires a relatively new version of Python 3 and the Python toml module. See the instruction in the autograder README.

You need to put the `grade` program on your `PATH`.

Assume you clone the autograder into `~/cs631`, so you have `~/cs631/autograder`.

You can do this on your Raspberry Pi by adding to your PATH variable at the end of your `~/.profile`:

`export PATH=$PATH:~/cs631/autograder`

You will need to restart your shell to get the updated `PATH`.

Run the grade program once to generate a default config file:

```
$ grade
```

Now edit the default config file which is located here:

```
~/.config/grade/config.toml
```

You need only the following option in this file:

```
testspath = "/home/pi/cs631/tests"
```

Now, with everything in place, you can use the autograder by changing to your project or lab directory:

```
$ cd ~/cs631/lab01
$ grade test -p lab01
```

Hopefully you will see something like this:

```
$ grade test -p lab01
. 01 02 03 04 05 06 07 100/100
```

If you miss points you can run the grade program in verbose mode to see how your output differs from the expected output:

```
$ grade test -p lab01 -v
===[01]===actual
TK_INTLIT("1")
TK_EOT("")
===[01]===expected
TK_INTLIT("1")
TK_EOT("")
...
```
