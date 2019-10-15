---
description: Commanline mode with Cinema 4D R20 and upper
---

# Commanline mode

**File Sequence Exporter**, used with Cinema 4D version R20 and higher, can be run in _commandline mode_. This mode provides additional opportunities for integrating the plug-in in batch files and scripts. To do this, use the [**c4dpy.exe**](https://developers.maxon.net/docs/Cinema4DPythonSDK/html/manuals/introduction/python_c4dpy.html) utility.

```text
"c:\Program Files\MAXON\Cinema 4D R20\c4dpy.exe" -c "import c4d; c4d.CallCommand (1053078,1000)" -fse_settings "c:\Users\%USERNAME%\Desktop\export_settings.json"
```

Save Json-file with a plug-in parameters using menu **Help &gt; Save Settings To File**. 

![](../.gitbook/assets/image%20%281%29.png)

File will contain text as follows:

```javascript
{
	"fse_poly_lod": 100.0, 
	"fse_to_frame": 90, 
	"fse_poly_reduction": 0.0, 
	"fse_doc_path": "C:\\Users\\%USERNAME%\\Desktop\\file_to_export.c4d", 
	"fse_selected": false, 
	"fse_save_path": "C:\\Users\\%USERNAME%\\Desktop\\sequence_file", 
	"fse_connected": true, 
	"fse_time_range": "All", 
	"fse_show_results": false, 
	"fse_skip_hidden": true,
	"fse_shared_mtlfile":false, 
	"fse_from_frame": 0, 
	"fse_save_format": "c4d"
}
```



Parameters from the json-file can be overridden by specifying them as a separate option in the command:

```text
"c:\Program Files\MAXON\Cinema 4D R20\c4dpy.exe" -c "import c4d; c4d.CallCommand (1053078,1000)" -fse_settings "c:\Users\%USERNAME%\Desktop\export_settings.json" -fse_doc_path "C:\WorkFolder\other_file_to_export.c4d" -fse_show_results 1 -fse_time_range "Preview"
```

To get a full description of all plug-in commandline options, use **-h** option: 

```text
"c:\Program Files\MAXON\Cinema 4D R20\c4dpy.exe" -c "import c4d; c4d.CallCommand(1053078,1000)" -h
```

```typescript
C:\Users\%USERNAME%>"c:\Program Files\MAXON\Cinema 4D R20\c4dpy.exe" -c "import c4d; c4d.CallCommand(1053078,1000)" -h
usage: File Sequence Exporter v1.0 [-h] [-fse_settings FSE_SETTINGS]
                                   [-fse_doc_path FSE_DOC_PATH]
                                   [-fse_save_path FSE_SAVE_PATH]
                                   [-fse_save_format {c4d,obj}]
                                   [-fse_from_frame FSE_FROM_FRAME]
                                   [-fse_to_frame FSE_TO_FRAME]
                                   [-fse_poly_reduction FSE_POLY_REDUCTION]
                                   [-fse_poly_lod FSE_POLY_LOD]
                                   [-fse_selected {1,0}]
                                   [-fse_skip_hidden {1,0}]
                                   [-fse_connected {1,0}]
                                   [-fse_show_results {1,0}]
                                   [-fse_time_range {All,Preview,Manual,CurrentFrame}]

Export scene geometry to Cinema 4d or Obj file. This command starts File
Sequence Exporter in commandline mode.

optional arguments:
  -h, --help            show this help message and exit
  -fse_settings FSE_SETTINGS
                        Json file path with plug-in Export settings.
  -fse_doc_path FSE_DOC_PATH
                        Cinema 4D document file path.
  -fse_save_path FSE_SAVE_PATH
                        Exported file sequence path.
  -fse_save_format {c4d,obj}
                        File sequence format. Available values: c4d, obj.
  -fse_from_frame FSE_FROM_FRAME
                        Save From Frame.
  -fse_to_frame FSE_TO_FRAME
                        Save To Frame.
  -fse_poly_reduction FSE_POLY_REDUCTION
                        Polygon reduction value. (0-100)
  -fse_poly_lod FSE_POLY_LOD
                        Level Of Detail. (0-100)
  -fse_selected {1,0}   Export only selected objects.
  -fse_skip_hidden {1,0}
                        Skip hidden objects.
  -fse_connected {1,0}  Connect all objects to new one.
  -fse_show_results {1,0}
                        Show export results in Explorer/Finder after
                        exporting.
  -fse_time_range {All,Preview,Manual,CurrentFrame}
                        Timeline Frame range. Available values: All, Preview,
                        Manual, CurrentFrame.
```

![](../.gitbook/assets/image%20%282%29.png)





