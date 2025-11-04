>: Redirects standard output (overwrites file).
>>: Redirects and appends output to a file.
<: Takes input from a file instead of the keyboard.
2>: Redirects error messages to a file.
&>: Redirects both standard output and error to a file.

">>" standard output
"<<" standard input
 In the below-mentioned example, the file descriptor used above is 2(STDERR). Using "2>" re-directs the error output to a file named "error.txt" and nothing is displayed on STDOUT.

$ somerandomcommand 2>error.txt
error Redirection in linux
