
# Panda3D Module Builder

This is a prefab to create modules and extensions for the <a href="http://github.com/panda3d/panda3d">Panda3D</a> engine. It provides a cmake script to make building
and distributing your modules the matter of a single command / mouseclick.

## Requirements

- The Panda3D SDK (get it <a href="http://www.panda3d.org/download.php?sdk">here</a>)
- CMake 2.6 or higher (get it <a href="https://cmake.org/download/">here</a>)


**For compiling on Windows 32 bit:**

- Visual Studio 2010 (any version)

**For compiling on Windows 64 bit:**

- Visual Studio 2010 (any version)
- Windows SDK 7.1 (be sure to tick the VC++ 64 bit compilers)


**Notice:** If you want to use a different version of Visual Studio, you first need
to make a Panda3D build compiled with that version (otherwise your module won't work,
or crash randomly). After you did that, you can adjust the `config.ini` file with
your desired Visual Studio version. You can get a list of supported version strings
with `cmake --help`. Notice that you **don't have to specify `[arch]`** after the
Generator name, the script automatically does that, depending on your panda build architecture. 



## Usage


1. Copy the contents of this repository to a suitable path in your project
2. Move your C++ Code to the `Source/` directory.
3. To compile your module, use:

    ```
    python build.py
    ```

This will ask you for a module name the first time you run it. After that, it will generate a binary with the name `<module-name>.pyd` or `<module-name>.so` (depending on your platform) in the directory of the build script.

You can then simply import the module in python, like this:

```python
from insert_module_name_here import ExampleClass
test_class = ExampleClass()
```

There is also a small example class contained in the source directory, which shows the
basics of using interrogate.


## Further configuration

Further adjustments can be made in the `config.ini` file:

- You can set `generate_pdb` to `0` or `1` to control whether a .PDB file is generated.
- You can set `vc_version` to change the Visual Studio Version. See above!

Please cleanup your built directories after changing the configuration!

