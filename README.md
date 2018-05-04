<img src="folderz.svg" alt="Folderz">

List matching directories by file count.

Includes nested directories in file count but does not list child directories with same name.

## Why?

I wanted to find out the biggest node_modules folders on my system, ordered from
largest to smallest. I also didn't want to show seperate entries for nested node_modules folders.

Say you have the following structure

```
/myapp/
  node_modules/
    somePkg
        node_modules/
    somePkg2
      node_modules/
/myapp2/
  node_modules/
    somePkg
        node_modules/
/myapp3/
  node_modules/
    somePkg
```

Run this command to find all your largest node_modules directories and sort by size (and don't show nested children.)

```
folderz node_modules
```

Result

```
55 files in /myapp/node_modules
44 files in /myapp2/node_modules
33 files in /myapp3/node_modules
```

## Install

```
# GET
git clone https://github.com/lukeaus/folderz.git
cd folderz
// or copy folderz file and paste on your computer

# MAKE EXECUTABLE
chmod +x folderz

# RUN
./folderz some-search-term
// or add folderz to your PATH then
folderz some-search-term
```

## Usage

```
folderz [-d|--dir <arg>] [-p|--paths_only <arg>] [-q|--add_quotes <arg>] [-h|--help] <search_term>
```

## Examples

Find all the parent `node_modules` folders in your home directory and return sorted results

```
folderz node_modules -d ~
```

Find all the parent `node_modules` folders in your home directory and return sorted paths only

```
folderz node_modules -d ~ -p
```

Find all the `build` folders in your apps directory

```
folderz build -d ~/apps
```
