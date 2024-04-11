# JuliaApps: Simple and effective Julia's application workaround for unix based systems

At this moment, there is no standard way to create Julia applications. Different ways exist, but most approaches contain other limitations. This limitation may come from design because Julia includes a powerful REPL that makes CLI unnecessary for Julia practitioners.
However, people who do not work with Julia could find the Julian way unaccessible.

While we anticipate a more standardized approach to working with Julia's programs soon, I am glad to introduce JuliaApps (`japps`) as a solution today. This script aims to create Julia applications with minor modifications using isolated environments for each application so each app will work out of the box.


The script `japps` supports the following commands:
- `run`: runs a package as an application.
- `install`: installs a package from its GitHub URL.
- `uninstall` (still not implemented).
- `update`: updates a package and optionally checkouts some branch to work


# Installing


Clone this repository; `chmod +x japp`; copy `japp` to some directory in your executable path

This procedure only works for unix based systems

# How it works

JuliaApps is a bash script that helps to handle packages with entry points that can be called directly from command lines.
In particular, the idea is to install directly from git repositories and maintain an isolated environment for each package.
It is designed to be very simple and work with packages outside the Julia General registry.

The entry points are similar to those created by the [Comonincon.jl](https://comonicon.org/stable/) package; that is, it will call a module's function called `command_main(ARGS)`

Some working examples:
- <https://github.com/sadit/XGrep.jl>
- <https://github.com/sadit/NearDuplicates.jl>

By now, we don't have a curate list of applications.

# More help

```
japps --help

Install and run julia packages from command line easily

 usage: ./japps <commands> args...

 commands: run install uninstall update help

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
