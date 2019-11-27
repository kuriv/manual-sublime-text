# C++

成功配置 C 编译系统后，打开 Sublime Text ，选择 `Tools` - `Build System` - `New Build System...` ，然后添加下面的内容。

```json
{
    "cmd": "g++ -std=c++11 $file_name -o $file_base_name",
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "working_dir": "${file_path}",
    "selector": "source.c, source.c++",
    "shell": true,
    "encoding": "cp936",
    "variants": [{
        "name": "g++ Compile",
        "cmd": "g++ -std=c++11 $file_name -o $file_base_name"
    }, {
        "name": "g++ Run",
        "cmd": "start cmd /k $file_base_name"
    }]

}
```

将文件保存在默认的目录并命名为 `C++.sublime-build` ，重启 Sublime Text ，打开一个 C++ 文件，使用快捷键 `Ctrl + Shift + B` ，然后选择对应选项即可看到运行结果。