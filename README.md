# my-shell-commands
A list of shell commands that I use

# Find for ".csproj" that are not included in a solution
it will print the project name that is not included in the solution
```sh
cd /my/dir
find . -maxdepth 2 -type f -name "*.csproj" -printf '%f\n' | xargs -I % sh -c 'grep -q % AppSolution.sln || echo "%: N"'
```

`xargs -I` instruct the shell to execute each argument alone (in one line) here I am using the **%** as a placeholder
