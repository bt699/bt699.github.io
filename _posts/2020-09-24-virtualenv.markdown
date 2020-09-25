---
layout: post
title:  "virtualenv"
date:   2020-07-28 13:19:48 +0800
categories: python

---
# virtualenv #

Windows PowerShell
版权所有 (C) Microsoft Corporation。保留所有权利。

尝试新的跨平台 PowerShell https://aka.ms/pscore6

PS C:\Windows\system32> pip

Usage:
  pip <command> [options]

Commands:
  install                     Install packages.
  download                    Download packages.
  uninstall                   Uninstall packages.
  freeze                      Output installed packages in requirements format.
  list                        List installed packages.
  show                        Show information about installed packages.
  check                       Verify installed packages have compatible dependencies.
  config                      Manage local and global configuration.
  search                      Search PyPI for packages.
  cache                       Inspect and manage pip's wheel cache.
  wheel                       Build wheels from your requirements.
  hash                        Compute hashes of package archives.
  completion                  A helper command used for command completion.
  debug                       Show information useful for debugging.
  help                        Show help for commands.

General Options:
  -h, --help                  Show help.
  --isolated                  Run pip in an isolated mode, ignoring environment variables and user configuration.
  -v, --verbose               Give more output. Option is additive, and can be used up to 3 times.
  -V, --version               Show version and exit.
  -q, --quiet                 Give less output. Option is additive, and can be used up to 3 times (corresponding to
                              WARNING, ERROR, and CRITICAL logging levels).
  --log <path>                Path to a verbose appending log.
  --proxy <proxy>             Specify a proxy in the form [user:passwd@]proxy.server:port.
  --retries <retries>         Maximum number of retries each connection should attempt (default 5 times).
  --timeout <sec>             Set the socket timeout (default 15 seconds).
  --exists-action <action>    Default action when a path already exists: (s)witch, (i)gnore, (w)ipe, (b)ackup,
                              (a)bort.
  --trusted-host <hostname>   Mark this host or host:port pair as trusted, even though it does not have valid or any
                              HTTPS.
  --cert <path>               Path to alternate CA bundle.
  --client-cert <path>        Path to SSL client certificate, a single file containing the private key and the
                              certificate in PEM format.
  --cache-dir <dir>           Store the cache data in <dir>.
  --no-cache-dir              Disable the cache.
  --disable-pip-version-check
                              Don't periodically check PyPI to determine whether a new version of pip is available for
                              download. Implied with --no-index.
  --no-color                  Suppress colored output
  --no-python-version-warning
                              Silence deprecation warnings for upcoming unsupported Pythons.
PS C:\Windows\system32> pip -V
pip 20.1.1 from c:\users\zzt\appdata\local\programs\python\python37\lib\site-packages\pip (python 3.7)
PS C:\Windows\system32> pip install virtualven
ERROR: Could not find a version that satisfies the requirement virtualven (from versions: none)
ERROR: No matching distribution found for virtualven
WARNING: You are using pip version 20.1.1; however, version 20.2.3 is available.
You should consider upgrading via the 'c:\users\zzt\appdata\local\programs\python\python37\python.exe -m pip install --upgrade pip' command.
PS C:\Windows\system32> pip install virtualenv
Collecting virtualenv
  Downloading virtualenv-20.0.31-py2.py3-none-any.whl (4.9 MB)
     |████████████████████████████████| 4.9 MB 107 kB/s
Collecting distlib<1,>=0.3.1
  Downloading distlib-0.3.1-py2.py3-none-any.whl (335 kB)
     |████████████████████████████████| 335 kB 84 kB/s
Collecting appdirs<2,>=1.4.3
  Downloading appdirs-1.4.4-py2.py3-none-any.whl (9.6 kB)
Collecting importlib-metadata<2,>=0.12; python_version < "3.8"
  Downloading importlib_metadata-1.7.0-py2.py3-none-any.whl (31 kB)
Collecting filelock<4,>=3.0.0
  Downloading filelock-3.0.12-py3-none-any.whl (7.6 kB)
Requirement already satisfied: six<2,>=1.9.0 in c:\users\zzt\appdata\local\programs\python\python37\lib\site-packages (from virtualenv) (1.15.0)
Collecting zipp>=0.5
  Downloading zipp-3.2.0-py3-none-any.whl (5.1 kB)
Installing collected packages: distlib, appdirs, zipp, importlib-metadata, filelock, virtualenv
Successfully installed appdirs-1.4.4 distlib-0.3.1 filelock-3.0.12 importlib-metadata-1.7.0 virtualenv-20.0.31 zipp-3.2.0
WARNING: You are using pip version 20.1.1; however, version 20.2.3 is available.
You should consider upgrading via the 'c:\users\zzt\appdata\local\programs\python\python37\python.exe -m pip install --upgrade pip' command.
PS C:\Windows\system32> cd..
PS C:\Windows> cd..
PS C:\> cd reglogin
PS C:\reglogin> dir
PS C:\reglogin> virtualenv reglog
created virtual environment CPython3.7.8.final.0-64 in 16871ms
  creator CPython3Windows(dest=C:\reglogin\reglog, clear=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=C:\Users\zzt\AppData\Local\pypa\virtualenv)
    added seed packages: pip==20.2.2, setuptools==49.6.0, wheel==0.35.1
  activators BashActivator,BatchActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator
PS C:\reglogin> cd Scripts
cd : 找不到路径“C:\reglogin\Scripts”，因为该路径不存在。
所在位置 行:1 字符: 1
+ cd Scripts
+ ~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\reglogin\Scripts:String) [Set-Location], ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.SetLocationCommand

PS C:\reglogin> ls


    目录: C:\reglogin


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2020/9/25     10:15                reglog


PS C:\reglogin> cd reglog
PS C:\reglogin\reglog> ls


    目录: C:\reglogin\reglog


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2020/9/25     10:15                Lib
d-----        2020/9/25     10:15                Scripts
-a----        2020/9/25     10:15             42 .gitignore
-a----        2020/9/25     10:15            397 pyvenv.cfg


PS C:\reglogin\reglog> cd .\Scripts\
PS C:\reglogin\reglog\Scripts> activate
activate : 无法将“activate”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保
路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate
+ ~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> .\activate
.\activate : 无法加载文件 C:\reglogin\reglog\Scripts\activate.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 htt
ps:/go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。
所在位置 行:1 字符: 1
+ .\activate
+ ~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) []，PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
PS C:\reglogin\reglog\Scripts> .\activate
.\activate : 无法加载文件 C:\reglogin\reglog\Scripts\activate.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 htt
ps:/go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。
所在位置 行:1 字符: 1
+ .\activate
+ ~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) []，PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
PS C:\reglogin\reglog\Scripts> activate
activate : 无法将“activate”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保
路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate
+ ~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> activate.bat
activate.bat : 无法将“activate.bat”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径
，请确保路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate.bat
+ ~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate.bat:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate.bat，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate.bat”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> activate
activate : 无法将“activate”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保
路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate
+ ~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> ls


    目录: C:\reglogin\reglog\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2020/9/25     10:15           2295 activate
-a----        2020/9/25     10:15           1051 activate.bat
-a----        2020/9/25     10:15           3161 activate.fish
-a----        2020/9/25     10:15           1815 activate.ps1
-a----        2020/9/25     10:15           1198 activate.xsh
-a----        2020/9/25     10:15           1225 activate_this.py
-a----        2020/9/25     10:15            529 deactivate.bat
-a----        2020/9/25     10:15         106357 easy_install-3.7.exe
-a----        2020/9/25     10:15         106357 easy_install.exe
-a----        2020/9/25     10:15         106357 easy_install3.7.exe
-a----        2020/9/25     10:15         106357 easy_install3.exe
-a---l        2020/9/25     10:15              0 libcrypto-1_1.dll
-a---l        2020/9/25     10:15              0 libssl-1_1.dll
-a----        2020/9/25     10:15         106348 pip-3.7.exe
-a----        2020/9/25     10:15         106348 pip.exe
-a----        2020/9/25     10:15         106348 pip3.7.exe
-a----        2020/9/25     10:15         106348 pip3.exe
-a----        2020/9/25     10:15             25 pydoc.bat
-a---l        2020/9/25     10:15              0 pyexpat.pyd
-a---l        2020/9/25     10:15              0 python.exe
-a---l        2020/9/25     10:15              0 python3.dll
-a---l        2020/9/25     10:15              0 python37.dll
-a---l        2020/9/25     10:15              0 pythonw.exe
-a---l        2020/9/25     10:15              0 select.pyd
-a---l        2020/9/25     10:15              0 sqlite3.dll
-a---l        2020/9/25     10:15              0 tcl86t.dll
-a---l        2020/9/25     10:15              0 tk86t.dll
-a---l        2020/9/25     10:15              0 unicodedata.pyd
-a---l        2020/9/25     10:15              0 vcruntime140.dll
-a----        2020/9/25     10:15         106335 wheel-3.7.exe
-a----        2020/9/25     10:15         106335 wheel.exe
-a----        2020/9/25     10:15         106335 wheel3.7.exe
-a----        2020/9/25     10:15         106335 wheel3.exe
-a---l        2020/9/25     10:15              0 winsound.pyd
-a---l        2020/9/25     10:15              0 _asyncio.pyd
-a---l        2020/9/25     10:15              0 _bz2.pyd
-a---l        2020/9/25     10:15              0 _ctypes.pyd
-a---l        2020/9/25     10:15              0 _ctypes_test.pyd
-a---l        2020/9/25     10:15              0 _decimal.pyd
-a---l        2020/9/25     10:15              0 _elementtree.pyd
-a---l        2020/9/25     10:15              0 _hashlib.pyd
-a---l        2020/9/25     10:15              0 _lzma.pyd
-a---l        2020/9/25     10:15              0 _msi.pyd
-a---l        2020/9/25     10:15              0 _multiprocessing.pyd
-a---l        2020/9/25     10:15              0 _overlapped.pyd
-a---l        2020/9/25     10:15              0 _queue.pyd
-a---l        2020/9/25     10:15              0 _socket.pyd
-a---l        2020/9/25     10:15              0 _sqlite3.pyd
-a---l        2020/9/25     10:15              0 _ssl.pyd
-a---l        2020/9/25     10:15              0 _testbuffer.pyd
-a---l        2020/9/25     10:15              0 _testcapi.pyd
-a---l        2020/9/25     10:15              0 _testconsole.pyd
-a---l        2020/9/25     10:15              0 _testimportmultiple.pyd
-a---l        2020/9/25     10:15              0 _testmultiphase.pyd
-a---l        2020/9/25     10:15              0 _tkinter.pyd


PS C:\reglogin\reglog\Scripts> activate.bat
activate.bat : 无法将“activate.bat”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径
，请确保路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate.bat
+ ~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate.bat:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate.bat，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate.bat”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> .\activate.bat
PS C:\reglogin\reglog\Scripts> Set-ExecutionPolicy -ExecutionPolicy UNRESTRICTED

执行策略更改
执行策略可帮助你防止执行不信任的脚本。更改执行策略可能会产生安全风险，如 https:/go.microsoft.com/fwlink/?LinkID=135170
中的 about_Execution_Policies 帮助主题所述。是否要更改执行策略?
[Y] 是(Y)  [A] 全是(A)  [N] 否(N)  [L] 全否(L)  [S] 暂停(S)  [?] 帮助 (默认值为“N”): A
PS C:\reglogin\reglog\Scripts> activate.bat
activate.bat : 无法将“activate.bat”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径
，请确保路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate.bat
+ ~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate.bat:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate.bat，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate.bat”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> activate
activate : 无法将“activate”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保
路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate
+ ~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> .\activate.bat
PS C:\reglogin\reglog\Scripts> activate.bat
activate.bat : 无法将“activate.bat”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径
，请确保路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ activate.bat
+ ~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (activate.bat:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: 找不到命令 activate.bat，但它确实存在于当前位置。默认情况下，Windows PowerShell 不会从当前位置加载命令。如果信任此命令，请改为键入“.\activate.bat”。有关详细信息，请参阅 "get-help about_Command_Precedence"。
PS C:\reglogin\reglog\Scripts> cd。。
cd。。 : 无法将“cd。。”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保路径
正确，然后再试一次。
所在位置 行:1 字符: 1
+ cd。。
+ ~~~~
    + CategoryInfo          : ObjectNotFound: (cd。。:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\reglogin\reglog\Scripts> cd..
PS C:\reglogin\reglog> cd..
PS C:\reglogin> reglog\Script\activate
reglog\Script\activate : 无法加载模块“reglog”。有关详细信息，请运行“Import-Module reglog”。
所在位置 行:1 字符: 1
+ reglog\Script\activate
+ ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (reglog\Script\activate:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CouldNotAutoLoadModule

PS C:\reglogin> reglog\Script\activate.bat
reglog\Script\activate.bat : 无法加载模块“reglog”。有关详细信息，请运行“Import-Module reglog”。
所在位置 行:1 字符: 1
+ reglog\Script\activate.bat
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (reglog\Script\activate.bat:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CouldNotAutoLoadModule

PS C:\reglogin> ls


    目录: C:\reglogin


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2020/9/25     10:15                reglog


PS C:\reglogin> cd reglog
PS C:\reglogin\reglog> ls


    目录: C:\reglogin\reglog


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2020/9/25     10:15                Lib
d-----        2020/9/25     10:15                Scripts
-a----        2020/9/25     10:15             42 .gitignore
-a----        2020/9/25     10:15            397 pyvenv.cfg


PS C:\reglogin\reglog> cd Scripts
PS C:\reglogin\reglog\Scripts> ls


    目录: C:\reglogin\reglog\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2020/9/25     10:15           2295 activate
-a----        2020/9/25     10:15           1051 activate.bat
-a----        2020/9/25     10:15           3161 activate.fish
-a----        2020/9/25     10:15           1815 activate.ps1
-a----        2020/9/25     10:15           1198 activate.xsh
-a----        2020/9/25     10:15           1225 activate_this.py
-a----        2020/9/25     10:15            529 deactivate.bat
-a----        2020/9/25     10:15         106357 easy_install-3.7.exe
-a----        2020/9/25     10:15         106357 easy_install.exe
-a----        2020/9/25     10:15         106357 easy_install3.7.exe
-a----        2020/9/25     10:15         106357 easy_install3.exe
-a---l        2020/9/25     10:15              0 libcrypto-1_1.dll
-a---l        2020/9/25     10:15              0 libssl-1_1.dll
-a----        2020/9/25     10:15         106348 pip-3.7.exe
-a----        2020/9/25     10:15         106348 pip.exe
-a----        2020/9/25     10:15         106348 pip3.7.exe
-a----        2020/9/25     10:15         106348 pip3.exe
-a----        2020/9/25     10:15             25 pydoc.bat
-a---l        2020/9/25     10:15              0 pyexpat.pyd
-a---l        2020/9/25     10:15              0 python.exe
-a---l        2020/9/25     10:15              0 python3.dll
-a---l        2020/9/25     10:15              0 python37.dll
-a---l        2020/9/25     10:15              0 pythonw.exe
-a---l        2020/9/25     10:15              0 select.pyd
-a---l        2020/9/25     10:15              0 sqlite3.dll
-a---l        2020/9/25     10:15              0 tcl86t.dll
-a---l        2020/9/25     10:15              0 tk86t.dll
-a---l        2020/9/25     10:15              0 unicodedata.pyd
-a---l        2020/9/25     10:15              0 vcruntime140.dll
-a----        2020/9/25     10:15         106335 wheel-3.7.exe
-a----        2020/9/25     10:15         106335 wheel.exe
-a----        2020/9/25     10:15         106335 wheel3.7.exe
-a----        2020/9/25     10:15         106335 wheel3.exe
-a---l        2020/9/25     10:15              0 winsound.pyd
-a---l        2020/9/25     10:15              0 _asyncio.pyd
-a---l        2020/9/25     10:15              0 _bz2.pyd
-a---l        2020/9/25     10:15              0 _ctypes.pyd
-a---l        2020/9/25     10:15              0 _ctypes_test.pyd
-a---l        2020/9/25     10:15              0 _decimal.pyd
-a---l        2020/9/25     10:15              0 _elementtree.pyd
-a---l        2020/9/25     10:15              0 _hashlib.pyd
-a---l        2020/9/25     10:15              0 _lzma.pyd
-a---l        2020/9/25     10:15              0 _msi.pyd
-a---l        2020/9/25     10:15              0 _multiprocessing.pyd
-a---l        2020/9/25     10:15              0 _overlapped.pyd
-a---l        2020/9/25     10:15              0 _queue.pyd
-a---l        2020/9/25     10:15              0 _socket.pyd
-a---l        2020/9/25     10:15              0 _sqlite3.pyd
-a---l        2020/9/25     10:15              0 _ssl.pyd
-a---l        2020/9/25     10:15              0 _testbuffer.pyd
-a---l        2020/9/25     10:15              0 _testcapi.pyd
-a---l        2020/9/25     10:15              0 _testconsole.pyd
-a---l        2020/9/25     10:15              0 _testimportmultiple.pyd
-a---l        2020/9/25     10:15              0 _testmultiphase.pyd
-a---l        2020/9/25     10:15              0 _tkinter.pyd


PS C:\reglogin\reglog\Scripts> .\activate
(reglog) PS C:\reglogin\reglog\Scripts> pip

Usage:
  pip <command> [options]

Commands:
  install                     Install packages.
  download                    Download packages.
  uninstall                   Uninstall packages.
  freeze                      Output installed packages in requirements format.
  list                        List installed packages.
  show                        Show information about installed packages.
  check                       Verify installed packages have compatible dependencies.
  config                      Manage local and global configuration.
  search                      Search PyPI for packages.
  cache                       Inspect and manage pip's wheel cache.
  wheel                       Build wheels from your requirements.
  hash                        Compute hashes of package archives.
  completion                  A helper command used for command completion.
  debug                       Show information useful for debugging.
  help                        Show help for commands.

General Options:
  -h, --help                  Show help.
  --isolated                  Run pip in an isolated mode, ignoring environment variables and user configuration.
  -v, --verbose               Give more output. Option is additive, and can be used up to 3 times.
  -V, --version               Show version and exit.
  -q, --quiet                 Give less output. Option is additive, and can be used up to 3 times (corresponding to
                              WARNING, ERROR, and CRITICAL logging levels).
  --log <path>                Path to a verbose appending log.
  --no-input                  Disable prompting for input.
  --proxy <proxy>             Specify a proxy in the form [user:passwd@]proxy.server:port.
  --retries <retries>         Maximum number of retries each connection should attempt (default 5 times).
  --timeout <sec>             Set the socket timeout (default 15 seconds).
  --exists-action <action>    Default action when a path already exists: (s)witch, (i)gnore, (w)ipe, (b)ackup,
                              (a)bort.
  --trusted-host <hostname>   Mark this host or host:port pair as trusted, even though it does not have valid or any
                              HTTPS.
  --cert <path>               Path to alternate CA bundle.
  --client-cert <path>        Path to SSL client certificate, a single file containing the private key and the
                              certificate in PEM format.
  --cache-dir <dir>           Store the cache data in <dir>.
  --no-cache-dir              Disable the cache.
  --disable-pip-version-check
                              Don't periodically check PyPI to determine whether a new version of pip is available for
                              download. Implied with --no-index.
  --no-color                  Suppress colored output
  --no-python-version-warning
                              Silence deprecation warnings for upcoming unsupported Pythons.
  --use-feature <feature>     Enable new functionality, that may be backward incompatible.
  --use-deprecated <feature>  Enable deprecated functionality, that will be removed in the future.
(reglog) PS C:\reglogin\reglog\Scripts> pip install flask-login
Collecting flask-login
  Downloading Flask_Login-0.5.0-py2.py3-none-any.whl (16 kB)
Collecting Flask
  Downloading Flask-1.1.2-py2.py3-none-any.whl (94 kB)
     |████████████████████████████████| 94 kB 280 kB/s
Collecting Werkzeug>=0.15
  Downloading Werkzeug-1.0.1-py2.py3-none-any.whl (298 kB)
     |████████████████████████████████| 298 kB 119 kB/s
Collecting click>=5.1
  Downloading click-7.1.2-py2.py3-none-any.whl (82 kB)
     |████████████████████████████████| 82 kB 85 kB/s
Collecting Jinja2>=2.10.1
  Downloading Jinja2-2.11.2-py2.py3-none-any.whl (125 kB)
     |████████████████████████████████| 125 kB 91 kB/s
Collecting itsdangerous>=0.24
  Downloading itsdangerous-1.1.0-py2.py3-none-any.whl (16 kB)
Collecting MarkupSafe>=0.23
  Downloading MarkupSafe-1.1.1-cp37-cp37m-win_amd64.whl (16 kB)
Installing collected packages: Werkzeug, click, MarkupSafe, Jinja2, itsdangerous, Flask, flask-login
Successfully installed Flask-1.1.2 Jinja2-2.11.2 MarkupSafe-1.1.1 Werkzeug-1.0.1 click-7.1.2 flask-login-0.5.0 itsdangerous-1.1.0
WARNING: You are using pip version 20.2.2; however, version 20.2.3 is available.
You should consider upgrading via the 'C:\reglogin\reglog\Scripts\python.exe -m pip install --upgrade pip' command.
(reglog) PS C:\reglogin\reglog\Scripts> cd..
(reglog) PS C:\reglogin\reglog> cd .\login_flask\
(reglog) PS C:\reglogin\reglog\login_flask> python runserver.py
Traceback (most recent call last):
  File "runserver.py", line 2, in <module>
    from login import userRoute
  File "C:\reglogin\reglog\login_flask\login.py", line 5, in <module>
    from model.user_model import User
  File "C:\reglogin\reglog\login_flask\model\__init__.py", line 4, in <module>
    from common import db
  File "C:\reglogin\reglog\login_flask\common\__init__.py", line 2, in <module>
    from flask_sqlalchemy import SQLAlchemy
ModuleNotFoundError: No module named 'flask_sqlalchemy'
(reglog) PS C:\reglogin\reglog\login_flask> cd..
(reglog) PS C:\reglogin\reglog> cd .\Scripts\
(reglog) PS C:\reglogin\reglog\Scripts> pip install flask_sqlalchemy
Collecting flask_sqlalchemy
  Downloading Flask_SQLAlchemy-2.4.4-py2.py3-none-any.whl (17 kB)
Requirement already satisfied: Flask>=0.10 in c:\reglogin\reglog\lib\site-packages (from flask_sqlalchemy) (1.1.2)
Collecting SQLAlchemy>=0.8.0
  Downloading SQLAlchemy-1.3.19-cp37-cp37m-win_amd64.whl (1.2 MB)
     |████████████████████████████████| 1.2 MB 74 kB/s
Requirement already satisfied: itsdangerous>=0.24 in c:\reglogin\reglog\lib\site-packages (from Flask>=0.10->flask_sqlalchemy) (1.1.0)
Requirement already satisfied: Werkzeug>=0.15 in c:\reglogin\reglog\lib\site-packages (from Flask>=0.10->flask_sqlalchemy) (1.0.1)
Requirement already satisfied: click>=5.1 in c:\reglogin\reglog\lib\site-packages (from Flask>=0.10->flask_sqlalchemy) (7.1.2)
Requirement already satisfied: Jinja2>=2.10.1 in c:\reglogin\reglog\lib\site-packages (from Flask>=0.10->flask_sqlalchemy) (2.11.2)
Requirement already satisfied: MarkupSafe>=0.23 in c:\reglogin\reglog\lib\site-packages (from Jinja2>=2.10.1->Flask>=0.10->flask_sqlalchemy) (1.1.1)
Installing collected packages: SQLAlchemy, flask-sqlalchemy
Successfully installed SQLAlchemy-1.3.19 flask-sqlalchemy-2.4.4
WARNING: You are using pip version 20.2.2; however, version 20.2.3 is available.
You should consider upgrading via the 'C:\reglogin\reglog\Scripts\python.exe -m pip install --upgrade pip' command.
(reglog) PS C:\reglogin\reglog\Scripts> cd..
(reglog) PS C:\reglogin\reglog> cd .\login_flask\
(reglog) PS C:\reglogin\reglog\login_flask> python runserver.py
Traceback (most recent call last):
  File "runserver.py", line 2, in <module>
    from login import userRoute
  File "C:\reglogin\reglog\login_flask\login.py", line 7, in <module>
    from form.login_form import LoginForm
  File "C:\reglogin\reglog\login_flask\form\login_form.py", line 2, in <module>
    from flask_wtf import FlaskForm as Form
ModuleNotFoundError: No module named 'flask_wtf'
(reglog) PS C:\reglogin\reglog\login_flask> cd..
(reglog) PS C:\reglogin\reglog> cd .\Scripts\
(reglog) PS C:\reglogin\reglog\Scripts> pip intall flask_wtf
ERROR: unknown command "intall" - maybe you meant "install"
(reglog) PS C:\reglogin\reglog\Scripts> pip install flask_wtf
Collecting flask_wtf
  Downloading Flask_WTF-0.14.3-py2.py3-none-any.whl (13 kB)
Collecting WTForms
  Downloading WTForms-2.3.3-py2.py3-none-any.whl (169 kB)
     |████████████████████████████████| 169 kB 107 kB/s
Requirement already satisfied: Flask in c:\reglogin\reglog\lib\site-packages (from flask_wtf) (1.1.2)
Requirement already satisfied: itsdangerous in c:\reglogin\reglog\lib\site-packages (from flask_wtf) (1.1.0)
Requirement already satisfied: MarkupSafe in c:\reglogin\reglog\lib\site-packages (from WTForms->flask_wtf) (1.1.1)
Requirement already satisfied: Werkzeug>=0.15 in c:\reglogin\reglog\lib\site-packages (from Flask->flask_wtf) (1.0.1)
Requirement already satisfied: click>=5.1 in c:\reglogin\reglog\lib\site-packages (from Flask->flask_wtf) (7.1.2)
Requirement already satisfied: Jinja2>=2.10.1 in c:\reglogin\reglog\lib\site-packages (from Flask->flask_wtf) (2.11.2)
Installing collected packages: WTForms, flask-wtf
Successfully installed WTForms-2.3.3 flask-wtf-0.14.3
WARNING: You are using pip version 20.2.2; however, version 20.2.3 is available.
You should consider upgrading via the 'C:\reglogin\reglog\Scripts\python.exe -m pip install --upgrade pip' command.
(reglog) PS C:\reglogin\reglog\Scripts> cd ..
(reglog) PS C:\reglogin\reglog> ls


    目录: C:\reglogin\reglog


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2020/9/25     10:44                amuxia-py_study-master
d-----        2020/9/25     10:15                Lib
d-----        2020/9/25     10:45                login_flask
d-----        2020/9/25     10:32                Scripts
-a----        2020/9/25     10:15             42 .gitignore
-a----        2020/9/25     10:42          45633 amuxia-py_study-master.zip
-a----        2020/9/25     10:15            397 pyvenv.cfg


(reglog) PS C:\reglogin\reglog> cd login_flask
(reglog) PS C:\reglogin\reglog\login_flask> python runserver.py
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Serving Flask app "model" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Restarting with stat
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Debugger is active!
 * Debugger PIN: 315-989-031
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [25/Sep/2020 11:11:33] "[33mGET / HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 11:11:34] "[33mGET /favicon.ico HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 11:18:50] "[33mGET /login HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 11:26:48] "[33mGET /login.html HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 11:27:05] "[33mGET /user/login.html HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 11:29:13] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 11:29:13] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 11:29:28] "[35m[1mPOST /user/login HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\_collections.py", line 1020, in __call__
    return self.registry[key]
KeyError: 8696

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2464, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2450, in wsgi_app
    response = self.handle_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1867, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2447, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1952, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1821, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1950, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1936, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\reglogin\reglog\login_flask\login.py", line 34, in login
    user = User.query.filter(User.accountNumber == form.accountNumber.data,
  File "C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py", line 514, in __get__
    return type.query_class(mapper, session=self.sa.session())
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\scoping.py", line 78, in __call__
    return self.registry()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\_collections.py", line 1022, in __call__
    return self.registry.setdefault(key, self.createfunc())
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\session.py", line 3286, in __call__
    return self.class_(**local_kw)
  File "C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py", line 138, in __init__
    bind = options.pop('bind', None) or db.engine
  File "C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py", line 943, in engine
    return self.get_engine()
  File "C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py", line 962, in get_engine
    return connector.get_engine()
  File "C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py", line 556, in get_engine
    self._engine = rv = self._sa.create_engine(sa_url, options)
  File "C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py", line 972, in create_engine
    return sqlalchemy.create_engine(sa_url, **engine_opts)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\__init__.py", line 500, in create_engine
    return strategy.create(*args, **kwargs)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\strategies.py", line 87, in create
    dbapi = dialect_cls.dbapi(**dbapi_args)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\dialects\mysql\pymysql.py", line 62, in dbapi
    return __import__("pymysql")
ModuleNotFoundError: No module named 'pymysql'
127.0.0.1 - - [25/Sep/2020 11:29:29] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 11:29:29] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 11:29:29] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 11:29:31] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 11:29:31] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 11:29:31] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
(reglog) PS C:\reglogin\reglog\login_flask> cd ..
(reglog) PS C:\reglogin\reglog> cd .\Scripts\
(reglog) PS C:\reglogin\reglog\Scripts> pip install pymysql
Collecting pymysql
  Downloading PyMySQL-0.10.1-py2.py3-none-any.whl (47 kB)
     |████████████████████████████████| 47 kB 86 kB/s
Installing collected packages: pymysql
Successfully installed pymysql-0.10.1
WARNING: You are using pip version 20.2.2; however, version 20.2.3 is available.
You should consider upgrading via the 'C:\reglogin\reglog\Scripts\python.exe -m pip install --upgrade pip' command.
(reglog) PS C:\reglogin\reglog\Scripts> cd ..
(reglog) PS C:\reglogin\reglog> cd .\login_flask\
(reglog) PS C:\reglogin\reglog\login_flask> python runserver.py
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Serving Flask app "model" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Restarting with stat
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Debugger is active!
 * Debugger PIN: 315-989-031
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [25/Sep/2020 12:30:31] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:30:36] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 12:30:37] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 12:30:50] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:30:50] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 12:31:01] "[35m[1mPOST /user/login HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 2338, in _wrap_pool_connect
    return fn()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 364, in connect
    return _ConnectionFairy._checkout(self)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 778, in _checkout
    fairy = _ConnectionRecord.checkout(pool)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 495, in checkout
    rec = pool._do_get()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\impl.py", line 140, in _do_get
    self._dec_overflow()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\langhelpers.py", line 69, in __exit__
    exc_value, with_traceback=exc_tb,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\impl.py", line 137, in _do_get
    return self._create_connection()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 309, in _create_connection
    return _ConnectionRecord(self)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 440, in __init__
    self.__connect(first_connect_check=True)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 661, in __connect
    pool.logger.debug("Error on connect(): %s", e)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\langhelpers.py", line 69, in __exit__
    exc_value, with_traceback=exc_tb,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 656, in __connect
    connection = pool._invoke_creator(self)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\strategies.py", line 114, in connect
    return dialect.connect(*cargs, **cparams)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\default.py", line 493, in connect
    return self.dbapi.connect(*cargs, **cparams)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\__init__.py", line 94, in Connect
    return Connection(*args, **kwargs)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 327, in __init__
    self.connect()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 588, in connect
    self._request_authentication()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 853, in _request_authentication
    auth_packet = self._read_packet()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 676, in _read_packet
    packet.raise_for_error()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\protocol.py", line 223, in raise_for_error
    err.raise_mysql_exception(self._data)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\err.py", line 107, in raise_mysql_exception
    raise errorclass(errno, errval)
pymysql.err.OperationalError: (1049, "Unknown database 'rl_project'")

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2464, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2450, in wsgi_app
    response = self.handle_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1867, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2447, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1952, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1821, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1950, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1936, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\reglogin\reglog\login_flask\login.py", line 35, in login
    User.password == form.password.data).first()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3402, in first
    ret = list(self[0:1])
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3176, in __getitem__
    return list(res)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3508, in __iter__
    return self._execute_and_instances(context)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3530, in _execute_and_instances
    querycontext, self._connection_from_session, close_with_result=True
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3545, in _get_bind_args
    mapper=self._bind_mapper(), clause=querycontext.statement, **kw
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3523, in _connection_from_session
    conn = self.session.connection(**kw)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\session.py", line 1141, in connection
    execution_options=execution_options,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\session.py", line 1147, in _connection_for_bind
    engine, execution_options
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\session.py", line 433, in _connection_for_bind
    conn = bind._contextual_connect()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 2304, in _contextual_connect
    self._wrap_pool_connect(self.pool.connect, None),
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 2342, in _wrap_pool_connect
    e, dialect, self
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1584, in _handle_dbapi_exception_noconnection
    sqlalchemy_exception, with_traceback=exc_info[2], from_=e
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 2338, in _wrap_pool_connect
    return fn()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 364, in connect
    return _ConnectionFairy._checkout(self)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 778, in _checkout
    fairy = _ConnectionRecord.checkout(pool)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 495, in checkout
    rec = pool._do_get()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\impl.py", line 140, in _do_get
    self._dec_overflow()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\langhelpers.py", line 69, in __exit__
    exc_value, with_traceback=exc_tb,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\impl.py", line 137, in _do_get
    return self._create_connection()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 309, in _create_connection
    return _ConnectionRecord(self)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 440, in __init__
    self.__connect(first_connect_check=True)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 661, in __connect
    pool.logger.debug("Error on connect(): %s", e)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\langhelpers.py", line 69, in __exit__
    exc_value, with_traceback=exc_tb,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\pool\base.py", line 656, in __connect
    connection = pool._invoke_creator(self)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\strategies.py", line 114, in connect
    return dialect.connect(*cargs, **cparams)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\default.py", line 493, in connect
    return self.dbapi.connect(*cargs, **cparams)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\__init__.py", line 94, in Connect
    return Connection(*args, **kwargs)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 327, in __init__
    self.connect()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 588, in connect
    self._request_authentication()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 853, in _request_authentication
    auth_packet = self._read_packet()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 676, in _read_packet
    packet.raise_for_error()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\protocol.py", line 223, in raise_for_error
    err.raise_mysql_exception(self._data)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\err.py", line 107, in raise_mysql_exception
    raise errorclass(errno, errval)
sqlalchemy.exc.OperationalError: (pymysql.err.OperationalError) (1049, "Unknown database 'rl_project'")
(Background on this error at: http://sqlalche.me/e/13/e3q8)
127.0.0.1 - - [25/Sep/2020 12:31:01] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:31:01] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:31:01] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:31:03] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:31:04] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:31:05] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:11] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:11] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 12:43:14] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:15] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 12:43:20] "[35m[1mPOST /user/login HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1277, in _execute_context
    cursor, statement, parameters, context
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\default.py", line 593, in do_execute
    cursor.execute(statement, parameters)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 163, in execute
    result = self._query(query)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 321, in _query
    conn.query(q)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 505, in query
    self._affected_rows = self._read_query_result(unbuffered=unbuffered)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 724, in _read_query_result
    result.read()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 1069, in read
    first_packet = self.connection._read_packet()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 676, in _read_packet
    packet.raise_for_error()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\protocol.py", line 223, in raise_for_error
    err.raise_mysql_exception(self._data)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\err.py", line 107, in raise_mysql_exception
    raise errorclass(errno, errval)
pymysql.err.ProgrammingError: (1146, "Table 'rl_project.tb_user' doesn't exist")

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2464, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2450, in wsgi_app
    response = self.handle_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1867, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2447, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1952, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1821, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1950, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1936, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\reglogin\reglog\login_flask\login.py", line 35, in login
    User.password == form.password.data).first()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3402, in first
    ret = list(self[0:1])
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3176, in __getitem__
    return list(res)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3508, in __iter__
    return self._execute_and_instances(context)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3533, in _execute_and_instances
    result = conn.execute(querycontext.statement, self._params)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1011, in execute
    return meth(self, multiparams, params)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\sql\elements.py", line 298, in _execute_on_connection
    return connection._execute_clauseelement(self, multiparams, params)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1130, in _execute_clauseelement
    distilled_params,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1317, in _execute_context
    e, statement, parameters, cursor, context
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1511, in _handle_dbapi_exception
    sqlalchemy_exception, with_traceback=exc_info[2], from_=e
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1277, in _execute_context
    cursor, statement, parameters, context
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\default.py", line 593, in do_execute
    cursor.execute(statement, parameters)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 163, in execute
    result = self._query(query)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 321, in _query
    conn.query(q)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 505, in query
    self._affected_rows = self._read_query_result(unbuffered=unbuffered)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 724, in _read_query_result
    result.read()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 1069, in read
    first_packet = self.connection._read_packet()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 676, in _read_packet
    packet.raise_for_error()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\protocol.py", line 223, in raise_for_error
    err.raise_mysql_exception(self._data)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\err.py", line 107, in raise_mysql_exception
    raise errorclass(errno, errval)
sqlalchemy.exc.ProgrammingError: (pymysql.err.ProgrammingError) (1146, "Table 'rl_project.tb_user' doesn't exist")
[SQL: SELECT tb_user.id AS tb_user_id, tb_user.`accountNumber` AS `tb_user_accountNumber`, tb_user.password AS tb_user_password, tb_user.name AS tb_user_name
FROM tb_user
WHERE tb_user.`accountNumber` = %(accountNumber_1)s AND tb_user.password = %(password_1)s
 LIMIT %(param_1)s]
[parameters: {'accountNumber_1': '1', 'password_1': '2', 'param_1': 1}]
(Background on this error at: http://sqlalche.me/e/13/f405)
127.0.0.1 - - [25/Sep/2020 12:43:21] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:21] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:21] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:22] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:22] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 12:43:22] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:09] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:09] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 13:33:24] "[35m[1mPOST /user/login HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1277, in _execute_context
    cursor, statement, parameters, context
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\default.py", line 593, in do_execute
    cursor.execute(statement, parameters)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 163, in execute
    result = self._query(query)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 321, in _query
    conn.query(q)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 505, in query
    self._affected_rows = self._read_query_result(unbuffered=unbuffered)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 724, in _read_query_result
    result.read()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 1069, in read
    first_packet = self.connection._read_packet()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 676, in _read_packet
    packet.raise_for_error()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\protocol.py", line 223, in raise_for_error
    err.raise_mysql_exception(self._data)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\err.py", line 107, in raise_mysql_exception
    raise errorclass(errno, errval)
pymysql.err.ProgrammingError: (1146, "Table 'rl_project.tb_user' doesn't exist")

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2464, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2450, in wsgi_app
    response = self.handle_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1867, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2447, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1952, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1821, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1950, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1936, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\reglogin\reglog\login_flask\login.py", line 35, in login
    User.password == form.password.data).first()
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3402, in first
    ret = list(self[0:1])
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3176, in __getitem__
    return list(res)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3508, in __iter__
    return self._execute_and_instances(context)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\orm\query.py", line 3533, in _execute_and_instances
    result = conn.execute(querycontext.statement, self._params)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1011, in execute
    return meth(self, multiparams, params)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\sql\elements.py", line 298, in _execute_on_connection
    return connection._execute_clauseelement(self, multiparams, params)
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1130, in _execute_clauseelement
    distilled_params,
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1317, in _execute_context
    e, statement, parameters, cursor, context
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1511, in _handle_dbapi_exception
    sqlalchemy_exception, with_traceback=exc_info[2], from_=e
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\util\compat.py", line 182, in raise_
    raise exception
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\base.py", line 1277, in _execute_context
    cursor, statement, parameters, context
  File "C:\reglogin\reglog\lib\site-packages\sqlalchemy\engine\default.py", line 593, in do_execute
    cursor.execute(statement, parameters)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 163, in execute
    result = self._query(query)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\cursors.py", line 321, in _query
    conn.query(q)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 505, in query
    self._affected_rows = self._read_query_result(unbuffered=unbuffered)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 724, in _read_query_result
    result.read()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 1069, in read
    first_packet = self.connection._read_packet()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\connections.py", line 676, in _read_packet
    packet.raise_for_error()
  File "C:\reglogin\reglog\lib\site-packages\pymysql\protocol.py", line 223, in raise_for_error
    err.raise_mysql_exception(self._data)
  File "C:\reglogin\reglog\lib\site-packages\pymysql\err.py", line 107, in raise_mysql_exception
    raise errorclass(errno, errval)
sqlalchemy.exc.ProgrammingError: (pymysql.err.ProgrammingError) (1146, "Table 'rl_project.tb_user' doesn't exist")
[SQL: SELECT tb_user.id AS tb_user_id, tb_user.`accountNumber` AS `tb_user_accountNumber`, tb_user.password AS tb_user_password, tb_user.name AS tb_user_name
FROM tb_user
WHERE tb_user.`accountNumber` = %(accountNumber_1)s AND tb_user.password = %(password_1)s
 LIMIT %(param_1)s]
[parameters: {'accountNumber_1': '1', 'password_1': '2', 'param_1': 1}]
(Background on this error at: http://sqlalche.me/e/13/f405)
127.0.0.1 - - [25/Sep/2020 13:33:25] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:25] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:25] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:26] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:26] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 13:33:26] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 14:07:39] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 14:07:47] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 14:07:48] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 14:07:51] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 14:07:51] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 14:07:56] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 14:07:56] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 14:08:03] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 14:08:03] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 15:57:42] "[37mPOST /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:57:42] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 15:57:56] "[33mGET /user/ HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 15:58:04] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:58:04] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
127.0.0.1 - - [25/Sep/2020 15:58:11] "[35m[1mPOST /user/login HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2464, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2450, in wsgi_app
    response = self.handle_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1867, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 2447, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1952, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1821, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\reglogin\reglog\lib\site-packages\flask\_compat.py", line 39, in reraise
    raise value
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1950, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\reglogin\reglog\lib\site-packages\flask\app.py", line 1936, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\reglogin\reglog\login_flask\login.py", line 37, in login
    login_user(user)
  File "C:\reglogin\reglog\lib\site-packages\flask_login\utils.py", line 169, in login_user
    user_id = getattr(user, current_app.login_manager.id_attribute)()
  File "C:\reglogin\reglog\login_flask\model\user_model.py", line 32, in get_id
    return unicode(self.user_id)
NameError: name 'unicode' is not defined
127.0.0.1 - - [25/Sep/2020 15:58:12] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:58:12] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:58:12] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:58:13] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:58:13] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 15:58:13] "[37mGET /user/login?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\reglogin\\reglog\\login_flask\\model\\user_model.py', reloading
 * Restarting with stat
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Debugger is active!
 * Debugger PIN: 315-989-031
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
(reglog) PS C:\reglogin\reglog\login_flask> python runserver.py
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Serving Flask app "model" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Restarting with stat
C:\reglogin\reglog\lib\site-packages\flask_sqlalchemy\__init__.py:834: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
 * Debugger is active!
 * Debugger PIN: 315-989-031
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [25/Sep/2020 16:04:09] "[37mGET /user/login HTTP/1.1[0m" 200 -
127.0.0.1 - - [25/Sep/2020 16:04:09] "[33mGET /static/jquery1.42.min.js HTTP/1.1[0m" 404 -
^^^^^^^^^^^^^^^^^^^^^^^^
127.0.0.1 - - [25/Sep/2020 16:04:17] "[37mPOST /user/login HTTP/1.1[0m" 200 -
