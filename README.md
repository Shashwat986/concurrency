Concurrency Test
================

This is just a little bit of code I thought I could work with to make operations run concurrently. It isn't scalable, and has lots of problems besides. However, it's an interesting piece of code to explain message-passing between operations.

- - -

### initiator.py

This file writes a command (taken from stdin) and writes it to `input.txt`. It then waits for `runner.py` to return the output by checking `output.txt`, which it then displays.

### runner.py

This file keeps running in the background, waiting for `input.txt` to change. Once it detects that the file has changed, it reads it, runs the `exec` command in the input, and writes the result to `output.txt`.

