Configure
====

> A tiny bash script for managing simple rust dependencies. Used in Iron.


## Usage

* Use `rust-empty` to generate your project.
* Copy `configure` to your project.
* Add dependencies like so to the bottom of `configure`:

```
# Get target subfolder generated by rust-empty
TARGET=`rustc --version 2> /dev/null | awk '/host:/ { FS = " "; print $2 }'`

updateDependency "https://github.com/iron/iron" "iron" "target/$TARGET/lib"
```

This will add iron as a dependency of your project.