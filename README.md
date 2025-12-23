# Touch - Windows Touch Utility

A Windows implementation of the UNIX `touch` utility that updates file and folder timestamps.

## Description

This utility sets the LastAccessed, DateModified, and Created timestamps of files (and optionally folders) to the current time. It's useful for updating file modification times without actually modifying the file contents.

## Building

### Requirements
- Visual Studio 2022 (or compatible version)
- Windows SDK

### Build Instructions
1. Open `touch.sln` in Visual Studio
2. Select **Release** configuration (this is the default)
3. Build the solution (F7 or Build → Build Solution)
4. The executable `touch.exe` will be created in the same folder as the solution file

Alternatively, build from the command line:
```
msbuild touch.sln /p:Configuration=Release
```

## Usage

```
touch [options] [filespec]
```

### Options
- `-r` - Recursively process subdirectories
- `-v` - Verbose mode (show old/new timestamps)
- `-f` - Touch folders as well as files

### Examples

Touch all .exe files in current directory:
```
touch *.exe
```

Touch all .txt files recursively:
```
touch -r *.txt
```

Touch a file with verbose output:
```
touch -v readme.md
```

Touch all files and folders in current directory:
```
touch -f *
```

Touch all files and folders recursively:
```
touch -r -f
```

Touch all .log files and folders recursively with verbose output:
```
touch -r -v -f *.log
```

## Notes

- Running `touch` without any arguments displays usage information
- The default filespec (if not specified) is `*` (all files)
- Timestamps are set to the current system time
- Requires appropriate permissions to modify file/folder timestamps

## License

This is free software. Use it as you wish.
