# Cargo - default package manager for Rust

`cargo [OPTIONS] [SUBCOMMAND]`

OPTIONS:  
    `-V`, `--version`           Print version info and exit  
        `--list`              List installed commands  
        `--explain <CODE>`    Run `rustc --explain CODE`  
    `-v, --verbose`           Use verbose output (-vv very verbose/build.rs output)  
    `-q, --quiet`             No output printed to stdout  
        `--color <WHEN>`      Coloring: auto, always, never  
        `--frozen`            Require Cargo.lock and cache are up to date  
        `--locked`            Require Cargo.lock is up to date  
        `--offline`           Run without accessing the network  
    `-Z <FLAG>...`            Unstable (nightly-only) flags to Cargo, see 'cargo -Z help' for details  
    `-h, --help`              Prints help information  


Some common cargo commands:  
    `build`       Compile the current package  
    `check`       Analyze the current package and report errors, but don't build object files  
    `clean`       Remove the target directory  
    `doc`         Build this package's and its dependencies' documentation  
    `new`         Create a new cargo package  
    `init`        Create a new cargo package in an existing directory  
    `run`         Run a binary or example of the local package  
    `test`        Run the tests  
    `bench`       Run the benchmarks  
    `update`      Update dependencies listed in Cargo.lock  
    `search`      Search registry for crates  
    `publish`     Package and upload this package to the registry  
    `install`     Install a Rust binary. Default location is $HOME/.cargo/bin  
    `uninstall`   Uninstall a Rust binary  


See `cargo help <command>` for more information on a specific command.  

