Cargo support for Unikraft
===================
This library provides the necessary build rules to integrate Cargo projects into unikraft.

To add a cargo project simply add the `toml` file in the `Makefile.uk` of the library/application.

`APP_SRCS-y += $(APP_BASE)/cargo_project/Cargo.toml`

The crate should be set to `staticlib` in the `toml` file:

```
[lib]
crate-type = ["staticlib"]
```

And you should add the unikrat internal rust library as a dependency:

```
[dependencies]
ukrust = { path = "../../../unikraft/lib/ukrust/" }
```

Finally, include the unikraft crate (for the panic handler and basic rust functionalities)

```
use ukrust;
```
