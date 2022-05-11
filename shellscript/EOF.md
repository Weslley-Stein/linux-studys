#EOF
On shell we can use inline "text" as the input for a command, such as
```sh
cat << EOF
> write
> anything
> you
> want
> EOF
# Output: 
# write
# anything
# you
# want
```
- OBS: the "EOF" could be anything, that its just a word to determine where the 
text begin and where its stop

