# C

将 C 添加至环境变量，打开 Sublime Text ，选择 `Tools` - `Build System` - `New Build System...` ，然后添加下面的内容。

```json
{
    "cmd": ["g++", "${file}", "-o", "${file_path}/${file_base_name}"],
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:?(.*)$",
    "working_dir": "${file_path}",
    "encoding": "cp936",
    "selector": "source.c",
    "variants": [{
        "name": "Run",
        "cmd": ["cmd", "/C", "start", "cmd", "/c", "${file_path}/${file_base_name}.exe &pause"]
    }]
}
```

将文件保存在默认的目录并命名为 `C.sublime-build` ，重启 Sublime Text ，打开一个 C 文件，使用快捷键 `Ctrl + Shift + B` ，然后选择对应选项即可看到运行结果。