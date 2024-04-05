# JuliaApps: Simple and effective Julia's application workaround for unix based systems


Julia applications are not standardized at this moment. There exists different ways to achieve it but most approaches contain different limitations,
most of them are because Julia includes a very interesting and powerful REPL and people working in Julia seems that is not urgent to have another kind of CLI for their programs.
However, people not working with Julia but only trying to use the programs have a very different opinion.
While it is expected to have a more standard way to work with Julia's programs soon, I decide to put another piece in the board.


It consist on a single bash script `japps` that supports some commands:
- `run`: runs a package as an application
- `install`: installs a package from its github url
- `uninstall` (not really working for safety reasons)
- `update`: updates a package and optionally checkouts some branch to work


# Installing


Clone this repository; `chmod +x japp`; copy `japp` to some directory in your executable path

This procedure only works for unix based systems

# How it works

JuliaApps is a bash script that help to handle packages with entry points that can be called directly from command lines.
In particular, the idea is to install directly from git repositories and maintain an isolated environment for each package.
It is designed to be very simple, and working with packages that can be outside of the Julia General registry.

The entry points are similar to those created by the [Comonincon.jl](https://comonicon.org/stable/) package, that is, it will call a modele's function called `command_main(ARGS)`

Some working examples:
- <https://github.com/sadit/XGrep.jl>
- <https://github.com/sadit/NearDuplicates.JuliaApps>


# More help

```
./japps --help

Install and run julia packages from command line easily

 usage: ./japps <commands> args...

 commands: run install unistall update help

 run app-name args...
    runs an application with the given arguments

 install url-app-repo
    install the app cloning the git repository in the application directory and initializes the directory

 uninstall app-name
    removes the app git local repository

 update app-name [branch or tag]
    updates the app using a pull on the app repository

 INFO:
 Julia-Apps directory: /home/sadit/.julia/Apps
 Julia-Binary: /home/sadit/.juliaup/bin/julia
```
