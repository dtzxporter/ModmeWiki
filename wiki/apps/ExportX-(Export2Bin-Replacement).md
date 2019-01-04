# ExportX (Export2Bin Replacement)
Converts `_export` files to `_bin` files and `vise-versa`

## [>> Download <<](http://aviacreations.com/wraith/#utilities-view)

## Usage
Either `Drag and Drop` file(s) onto the program, or use the command line -f to specify a file or folder of files to convert.

## Commands
Below are the currently available commands:

| Name | Usage | Example
| ----- | ----- | -----
| (f) file | Specify input the file, or directory | -f "C:\Wraith\exported_files"
| (o) out | Specify output file, or directory | -o "C:\ConvertedFiles"
| (m) mode | Specify input mode (export, bin) | -m export
| (w) watcher | Startup a file watcher for new bin/export files | -f "C:\Wraith\exported_files" -w

## Watcher Mode (ExportX v2.0)
Watcher mode is very useful when combined with Wraith's `XMODEL` exporter, you can create a shortcut for ExportX that monitors the Wraith export directory and automatically creates a `_bin` file for you.

- To create a shortcut, right click on ExportX and go to `Send To->Desktop`
- Next, find the shortcut and go to properties
- In the target field, `AFTER` the last quote (") put the following:
```
-f "<Full Wraith Exported Files Path>" -w
```
- Example entry:
```
-f "C:\Wraith\exported_files" -w
```
- Click apply, then close. Launching this shortcut will create a watcher that will convert `xmodel_export` files automatically!
- You can close the dialog when you are finished.