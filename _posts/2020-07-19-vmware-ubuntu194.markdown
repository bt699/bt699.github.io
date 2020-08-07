---
layout: post
title:  "vmware-ubuntu194"
date:   2020-07-15 13:19:48 +0800
categories: python

---
# vmware-ubuntu194 #
用vmware安装ubuntu19.4时一直提示安装失败。
排查原因：必须选择【update to the new installer】即成功安装。不要选择【continue without updating】否作安装失败。
同时等更新完成会重启，在进入下一步就正常了
查看ubuntu的ip 答：ifconfig

替换源
sudo vi /etc/apt/sources.list

cn.archive.ubuntu.com/ubuntu替换为mirrors.aliyun.com
:%s#cn.archive.ubuntu.com/ubuntu#mirrors.aliyun.com/#g

:%s#aliyun.com#aliyun.com/ubuntu#g

:%s#aliyun.com/ubuntu#aliyun.com/ubuntu/#g

:%s#cn.archive.ubuntu.com/ubuntu#mirrors.aliyun.com/ubuntu#g

:%s#mirrors.aliyun.com/ubuntu/#cn.archive.ubuntu.com/ubuntu#g


复制20.4源文件
[](https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b11BskBlO)

保存退出
:wq

安装python27
$ sudo apt-get update

$ sudo apt-get install python2.7

$wget https://bootstrap.pypa.io/get-pip.py

$python2.7 get-pip.py

$python2.7 -m pip install paddlepaddle -i https://mirror.baidu.com/pypi/simple

ImportError: libgomp.so.1: cannot open shared object file: No such file or directory

$sudo apt-get install libgomp1

ImportError: libgomp.so.1: cannot open shared object file: No such file or directory

$sudo apt-get install libsm6 libxrender1 libfontconfig1

$python2.7

>>> import paddle.fluid
>>> paddle.fluid.install_check.run_check()
Running Verify Fluid Program ...
Your Paddle Fluid works well on SINGLE GPU or CPU.
W0719 05:59:28.002332 15488 build_strategy.cc:170] fusion_group is not enabled for Windows/MacOS now, and only effective when running with CUDA GPU.
W0719 05:59:28.003418 15488 fuse_all_reduce_op_pass.cc:74] Find all_reduce operators: 2. To make the speed faster, some all_reduce ops are fused during training, after fusion, the number of all_reduce ops is 1.
Your Paddle Fluid works well on MUTIPLE GPU or CPU.
Your Paddle Fluid is installed successfully! Let's start deep Learning with Paddle Fluid now

安装成功。

重启登录不上ssh

$ sudo apt-get install openssh-client

新建文件
sudo vi laji.py

访问网址
sudo apt-get install w3m

下载文件
wget http://192.168.230.1:8080/8047.zip

下载unzip
sudo apt install unzip

wget http://192.168.230.1:8080/webserver.zip

启动脚本
sudo sh ./start.sh

创建目录
sudo mkdir conf
sudo mkdir model


mkdir -p /home/work/paddle-predictor/resources/model
cp -r /home/work/paddle-predictor/$(dirname `find webserver/model/ -name '__model__' -type f`)/* /home/work/paddle-predictor/resources/model/
cp -r /home/work/paddle-predictor/webserver/model/freeze-model/* /home/work/paddle-predictor/resources/model/
cp -r ~/laji/webserver/model/freeze-model/* /home/work/paddle-predictor/resources/model/

安装django
python2.7 -m pip install django==1.11.4 -i https://mirror.baidu.com/pypi/simple

cp /home/work/paddle-predictor/webserver/server.conf /home/work/paddle-predictor/src/conf/server.conf

访问django
python2.7 manage.py runserver
File "/home/work/paddle-predictor/webserver/webserver/urls.py", line 19, in <module>
    from django.urls import re_path
ImportError: cannot import name re_path
排查原因:from django.urls import re_path应该是from django.conf.urls import url
路由部分也要path应该是url。完美成功运行。
urlpatterns = [
     url(正则表达式, views视图函数，参数),
]

安装pip install paddlehub -i https://mirror.baidu.com/pypi/simple

启动hub serving start -m vgg11_imagenet  

z@z:~$ hub serving start -m vgg11_imagenet
2020-07-21 07:34:50,720-INFO: font search path ['/home/z/.local/lib/python2.7/site-packages/matplotlib/mpl-data/fonts/ttf', '/home/z/.local/lib/python2.7/site-packages/matplotlib/mpl-data/fonts/afm', '/home/z/.local/lib/python2.7/site-packages/matplotlib/mpl-data/fonts/pdfcorefonts']
2020-07-21 07:34:52,136-INFO: generated new fontManager
Downloading vgg11_imagenet
[==================================================] 100.00%
Uncompress /home/z/.paddlehub/tmp/tmpyrBt9g/vgg11_imagenet
[==================================================] 100.00%
('vgg11_imagenet', '==', u'1.0.0')
 * Serving Flask app "paddlehub.serving.app_single" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
2020-07-21 07:38:51,052-INFO:  * Running on http://0.0.0.0:8866/ (Press CTRL+C to quit)
2020-07-21 08:37:46,944-INFO: 192.168.230.1 - - [21/Jul/2020 08:37:46] "POST / HTTP/1.1" 200 -

安装pip install requests -i https://mirror.baidu.com/pypi/simple

ERROR: Command errored out with exit status 1:
     command: /usr/bin/python2.7 -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-bIpdNC/ssl/setup.py'"'"'; __file__='"'"'/tmp/pip-install-bIpdNC/ssl/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base /tmp/pip-pip-egg-info-qpdQut
         cwd: /tmp/pip-install-bIpdNC/ssl/
    Complete output (5 lines):
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
      File "/tmp/pip-install-bIpdNC/ssl/setup.py", line 12, in <module>
        + "or earlier.")
    ValueError: This extension should not be used with Python 2.6 or later (already built in), and has not been tested with Python 2.3.4 or earlier.
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.

安装apt-get install libssl-dev

Traceback (most recent call last):
  File "H:/bushudog/vgg2.py", line 4, in <module>
    label_map = dataset.label_dict()
NameError: name 'dataset' is not defined
>>> import _ssl
>>> import requests
>>> import json
>>> file_list = ["H:\\bushudog\\test_img_cat.jpg", "H:\\bushudog\\test_img_dog.jpg"]
>>> files = [("image", (open(item, "rb"))) for item in file_list]

Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    files = [("image", (open(item, "rb"))) for item in file_list]
IOError: [Errno 2] No such file or directory: 'H:\\bushudog\\test_img_.jpg'
>>> file_list = ["H:\\bushudog\\test_img_cat.jpg", "H:\\bushudog\\test_img_dog.jpg"]
>>> files = [("image", (open(item, "rb"))) for item in file_list]
>>> url = "http://127.0.0.1:8866/"
>>> r = requests.post(url=url, files=files)

Traceback (most recent call last):
  File "<pyshell#8>", line 1, in <module>
    r = requests.post(url=url, files=files)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\api.py", line 119, in post
    return request('post', url, data=data, json=json, **kwargs)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\api.py", line 61, in request
    return session.request(method=method, url=url, **kwargs)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\sessions.py", line 530, in request
    resp = self.send(prep, **send_kwargs)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\sessions.py", line 643, in send
    r = adapter.send(request, **kwargs)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\adapters.py", line 516, in send
    raise ConnectionError(e, request=request)
ConnectionError: HTTPConnectionPool(host='127.0.0.1', port=8866): Max retries exceeded with url: / (Caused by NewConnectionError('<urllib3.connection.HTTPConnection object at 0x000000000AB2F048>: Failed to establish a new connection: [Errno 10061] ',))
>>> url = "http://192.168.230.132:8866/"
>>> r = requests.post(url=url, files=files)
>>> results = eval(r.json()["results"])

Traceback (most recent call last):
  File "<pyshell#11>", line 1, in <module>
    results = eval(r.json()["results"])
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\models.py", line 898, in json
    return complexjson.loads(self.text, **kwargs)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\json\__init__.py", line 339, in loads
    return _default_decoder.decode(s)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\json\decoder.py", line 364, in decode
    obj, end = self.raw_decode(s, idx=_w(s, 0).end())
  File "C:\Users\zrt\.windows-build-tools\python27\lib\json\decoder.py", line 382, in raw_decode
    raise ValueError("No JSON object could be decoded")
ValueError: No JSON object could be decoded
>>> print(json.dumps(results, indent=4, ensure_ascii=False))

Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    print(json.dumps(results, indent=4, ensure_ascii=False))
NameError: name 'results' is not defined
>>> results = r.json()

Traceback (most recent call last):
  File "<pyshell#13>", line 1, in <module>
    results = r.json()
  File "C:\Users\zrt\.windows-build-tools\python27\lib\site-packages\requests\models.py", line 898, in json
    return complexjson.loads(self.text, **kwargs)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\json\__init__.py", line 339, in loads
    return _default_decoder.decode(s)
  File "C:\Users\zrt\.windows-build-tools\python27\lib\json\decoder.py", line 364, in decode
    obj, end = self.raw_decode(s, idx=_w(s, 0).end())
  File "C:\Users\zrt\.windows-build-tools\python27\lib\json\decoder.py", line 382, in raw_decode
    raise ValueError("No JSON object could be decoded")
ValueError: No JSON object could be decoded
>>> r
<Response [200]>
>>> r.text
u'\n\n\n\n\n\n\n\n\n\n\n\n\n\n<!DOCTYPE html>\n<html lang="en">\n<head>\n    <meta charset="UTF-8">\n    <title>Hub-Serving</title>\n    <link rel="shortcut icon" href="https://paddlepaddle-org-cn.bj.bcebos.com/paddle-site-front/favicon.ico"/>\n    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">\n    <script src="https://code.jquery.com/jquery-3.4.1.min.js" integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" crossorigin="anonymous"></script>\n    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>\n</head>\n<body>\n<div class="input-group mb-3">\n    <table class="table table-striped table-dark table-hover">\n        <tr>\n            <td style="width: 17%"></td>\n            <td style="width: 5%" valign="top">\n                <label class="input-group-text" for="inputGroupSelect01" style="color: white;\n                background-color: rgba(0,0,0,0); border: 0px; font-size: 20px">\u5206\u7c7b\n                </label>\n            </td>\n            <td style="width: 25%">\n                <select class="custom-select" id="inputGroupSelect01"\n                        onchange="select_category(this.options[this.options.selectedIndex].value)">\n                    <option selected>Choose...</option>\n                </select>\n            </td>\n            <td style="width: 6%"></td>\n            <td style="width: 5%">\n                <label class="input-group-text" for="inputGroupSelect02" style="color: white;\n                background-color: rgba(0,0,0,0); border: 0px; font-size: 20px">\u6a21\u578b\n                </label>\n            </td>\n            <td style="width: 25%">\n                <select class="custom-select" id="inputGroupSelect02"\n                        onchange="select_module(this.options[this.options.selectedIndex].value)">\n                    <option selected value="Choose...">\u8bf7\u5148\u9009\u62e9\u5206\u7c7b...</option>\n                </select>\n            </td>\n            <td style="width: 17%"></td>\n        </tr>\n    </table>\n</div>\n<form id="main_form">\n    <div class="input-group mb-3" id="display_div">\n\n    </div>\n</form>\n<script>\n    var module_info = {};\n\n    $.ajax({\n        type: "POST",\n        url: "/get/modules",\n        data: "",\n        dataType: "json",\n        async: false,\n        success: function (res) {\n            module_info = res.module_info;\n            console.log(res);\n            console.log("mo=", module_info);\n            if (module_info.hasOwnProperty("nlp_module"))\n            {\n                s = document.getElementById("inputGroupSelect01");\n                s.options.add(new Option("nlp", "nlp_module"));\n            }\n            if (module_info.hasOwnProperty("cv_module"))\n            {\n                s = document.getElementById("inputGroupSelect01");\n                s.options.add(new Option("cv", "cv_module"));\n            }\n        }\n    });\n\n    function get_module_option(module_categoty) {\n        options = module_info[module_categoty];\n        html = "";\n        for (var i=0, len=options.length; i<len; i++){\n            option_name = Object.keys(options[i])[0];\n            option_value = options[i][option_name];\n            html = html\n            + "<option value=\'"\n            + option_value\n            + "\'>"\n            + option_name\n            + "</option>";\n        }\n        return html;\n    }\n    function get_single_text_html() {\n        html = ""\n        + \'<p style="width: 5%"></p>\'\n        + \'<p>\u8bf7\u8f93\u5165\u6587\u5b57\u6216\u8005\u4e0a\u4f20\u4e00\u4e2a\u6587\u672c\u6587\u4ef6</p>\'\n        + \'<p style="width: 2%"></p>\'\n        + \'<input type="file" id="file" onchange="handle_text(this.files)"/>\'\n        +\n            \'<table class="table table-striped table-dark table-hover" style="width: 95%"; align="center">\'\n            + \'<tr>\'\n                + \'<td>\'\n                    + \'<textarea cols="100" rows="30"\'\n                        + \'class="form-control"\'\n                        + \'id="file_text"\'\n                        + \'onblur="blur_input_text()"\'\n                        + \'onfocus="focus_input_text()"\'\n                        + \'name="text">\'\n                        + \'\u5728\u6b64\u952e\u5165\u6587\u672c\u6216\u4e0a\u4f20\u6587\u672c\u6587\u4ef6\'\n                    + \'</textarea>\'\n                + \'</td>\'\n                + \'<td>\'\n                    +\n            \'<input type="button" value="Go!" onclick="sub_text()" class="btn-circle"></input>\'\n                + \'</td>\'\n                + \'<td>\'\n                    + \'<textarea cols="100" rows="30"\'\n                        + \'class="form-control"\'\n                        + \'id="result_text"\'\n\n                        + \'name="result_text_name">\'\n\n                    + \'</textarea>\'\n                + \'</td>\'\n            + \'</tr>\'\n        + \'</table>\';\n        return html;\n    }\n    function blur_input_text()\n    {\n        text = document.getElementById("file_text");\n        if (text.value == ""){\n            text.value = "\u5728\u6b64\u952e\u5165\u6587\u672c\u6216\u4e0a\u4f20\u6587\u672c\u6587\u4ef6";\n        }\n    }\n    function focus_input_text(){\n        text = document.getElementById("file_text");\n        if (text.value == "\u5728\u6b64\u952e\u5165\u6587\u672c\u6216\u4e0a\u4f20\u6587\u672c\u6587\u4ef6"){\n            text.value = "";\n        }\n    }\n    function get_single_img_html() {\n        html = ""\n        + \'<p>\u8bf7\u4e0a\u4f20\u4e00\u4e2a\u56fe\u7247\u6587\u4ef6</p>\'\n        + \'<input type="file" id="file" onchange="handle_img(this.files)"/>\'\n        + \'<table class="table table-striped table-dark table-hover">\'\n            + \'<tr>\'\n                + \'<td style="width: 45%">\'\n                    + \'<img width="100%" id="file_img" name="input_img" value="kitten.jpg"/>\'\n                + \'</td>\'\n                + \'<td>\'\n                    + \'<input type="button" value="Start!" onclick="sub_img()"></input>\'\n                + \'</td>\'\n                + \'<td style="width: 45%"><table>\'\n                    + \'<tr><td>\'\n                        + \'<img width="100%" id="result_img" name="output_img"/>\'\n                    + \'</td></tr>\'\n                    + \'<tr><td>\'\n                        + \'<textarea cols="100" rows="2"\'\n                            + \'class="form-control"\'\n                            + \'id="result_text"\'\n                            + \'name="result_text_name">\'\n                        + \'</textarea>\'\n                    + \'</td></tr>\'\n                + \'</table></td>\'\n            + \'</tr>\'\n        + \'</table>\';\n        return html;\n    }\n    function select_category(module_categoty) {\n        select_module("Choose...");\n        option_html = get_module_option(module_categoty);\n        document.getElementById("inputGroupSelect02").innerHTML = option_html;\n    }\n    function select_module(module_name){\n        if (module_name == "Choose..."){\n            display_html = ""\n        }else{\n            if (document.getElementById("inputGroupSelect01").value == "nlp_module"){\n                display_html = get_single_text_html();\n            }else if (document.getElementById("inputGroupSelect01").value == "cv_module"){\n                display_html = get_single_img_html();\n            }\n\n        }\n        document.getElementById("display_div").innerHTML = display_html;\n    }\n    function handle_text(files) {\n        if (files.length){\n            let file = files[0];\n            let reader = new FileReader();\n            reader.onload = function(){\n                document.getElementById(\'file_text\').value = this.result;\n            };\n            reader.readAsText(file);\n        }\n    }\n    function handle_img(files) {\n        if (files.length){\n            let file = files[0];\n            let reader = new FileReader();\n            reader.onload = function(){\n                document.getElementById(\'file_img\').src = this.result;\n            };\n            reader.readAsDataURL(file);\n        }\n    }\n    function get_result_html(results) {\n        html = "";\n        for (var i=0, len=results.length; i<len; ++i){\n            html = html\n            + JSON.stringify(results[i])\n            + \'\\r\\n\'\n        }\n        return html;\n    }\n    function sub_text() {\n        var formParam = $("#main_form").serialize();\n        to_url = "/predict/text/" + document.getElementById("inputGroupSelect02").value;\n        $.ajax({\n                cache: true,\n                type: "POST",\n                url:to_url,\n                data:formParam,\n                async: false,\n                error: function(request) {\n                    alert("Connection error:"+request.error);\n                },\n                success: function(data) {\n                    console.log(data);\n                    html = get_result_html(data["results"]);\n                    document.getElementById("result_text").value = html;\n                }\n            });\n    }\n    function sub_img() {\n        var formParam = {\n            "image": document.getElementById("file_img").src,\n            "input_file":document.getElementById("file").value\n        };\n        to_url = "/predict/image/" + document.getElementById("inputGroupSelect02").value;\n        $.ajax({\n                cache: true,\n                type: "POST",\n                url:to_url,\n                data:formParam,\n                async: false,\n                error: function(request) {\n                    alert("Connection error:"+request.error);\n                },\n                success: function(data) {\n                    data = data.results;\n                    data = data.replace(/\'/g, \'"\');\n                    data = JSON.parse(data);\n                    data = data[0];\n\n                    document.getElementById("result_text").value = JSON.stringify(data.data[0]);\n                    document.getElementById("result_img").src = data.base64;\n                }\n            });\n    }\n</script>\n</body>\n</html>'
>>> r.content
'\n\n\n\n\n\n\n\n\n\n\n\n\n\n<!DOCTYPE html>\n<html lang="en">\n<head>\n    <meta charset="UTF-8">\n    <title>Hub-Serving</title>\n    <link rel="shortcut icon" href="https://paddlepaddle-org-cn.bj.bcebos.com/paddle-site-front/favicon.ico"/>\n    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">\n    <script src="https://code.jquery.com/jquery-3.4.1.min.js" integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" crossorigin="anonymous"></script>\n    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>\n</head>\n<body>\n<div class="input-group mb-3">\n    <table class="table table-striped table-dark table-hover">\n        <tr>\n            <td style="width: 17%"></td>\n            <td style="width: 5%" valign="top">\n                <label class="input-group-text" for="inputGroupSelect01" style="color: white;\n                background-color: rgba(0,0,0,0); border: 0px; font-size: 20px">\xe5\x88\x86\xe7\xb1\xbb\n                </label>\n            </td>\n            <td style="width: 25%">\n                <select class="custom-select" id="inputGroupSelect01"\n                        onchange="select_category(this.options[this.options.selectedIndex].value)">\n                    <option selected>Choose...</option>\n                </select>\n            </td>\n            <td style="width: 6%"></td>\n            <td style="width: 5%">\n                <label class="input-group-text" for="inputGroupSelect02" style="color: white;\n                background-color: rgba(0,0,0,0); border: 0px; font-size: 20px">\xe6\xa8\xa1\xe5\x9e\x8b\n                </label>\n            </td>\n            <td style="width: 25%">\n                <select class="custom-select" id="inputGroupSelect02"\n                        onchange="select_module(this.options[this.options.selectedIndex].value)">\n                    <option selected value="Choose...">\xe8\xaf\xb7\xe5\x85\x88\xe9\x80\x89\xe6\x8b\xa9\xe5\x88\x86\xe7\xb1\xbb...</option>\n                </select>\n            </td>\n            <td style="width: 17%"></td>\n        </tr>\n    </table>\n</div>\n<form id="main_form">\n    <div class="input-group mb-3" id="display_div">\n\n    </div>\n</form>\n<script>\n    var module_info = {};\n\n    $.ajax({\n        type: "POST",\n        url: "/get/modules",\n        data: "",\n        dataType: "json",\n        async: false,\n        success: function (res) {\n            module_info = res.module_info;\n            console.log(res);\n            console.log("mo=", module_info);\n            if (module_info.hasOwnProperty("nlp_module"))\n            {\n                s = document.getElementById("inputGroupSelect01");\n                s.options.add(new Option("nlp", "nlp_module"));\n            }\n            if (module_info.hasOwnProperty("cv_module"))\n            {\n                s = document.getElementById("inputGroupSelect01");\n                s.options.add(new Option("cv", "cv_module"));\n            }\n        }\n    });\n\n    function get_module_option(module_categoty) {\n        options = module_info[module_categoty];\n        html = "";\n        for (var i=0, len=options.length; i<len; i++){\n            option_name = Object.keys(options[i])[0];\n            option_value = options[i][option_name];\n            html = html\n            + "<option value=\'"\n            + option_value\n            + "\'>"\n            + option_name\n            + "</option>";\n        }\n        return html;\n    }\n    function get_single_text_html() {\n        html = ""\n        + \'<p style="width: 5%"></p>\'\n        + \'<p>\xe8\xaf\xb7\xe8\xbe\x93\xe5\x85\xa5\xe6\x96\x87\xe5\xad\x97\xe6\x88\x96\xe8\x80\x85\xe4\xb8\x8a\xe4\xbc\xa0\xe4\xb8\x80\xe4\xb8\xaa\xe6\x96\x87\xe6\x9c\xac\xe6\x96\x87\xe4\xbb\xb6</p>\'\n        + \'<p style="width: 2%"></p>\'\n        + \'<input type="file" id="file" onchange="handle_text(this.files)"/>\'\n        +\n            \'<table class="table table-striped table-dark table-hover" style="width: 95%"; align="center">\'\n            + \'<tr>\'\n                + \'<td>\'\n                    + \'<textarea cols="100" rows="30"\'\n                        + \'class="form-control"\'\n                        + \'id="file_text"\'\n                        + \'onblur="blur_input_text()"\'\n                        + \'onfocus="focus_input_text()"\'\n                        + \'name="text">\'\n                        + \'\xe5\x9c\xa8\xe6\xad\xa4\xe9\x94\xae\xe5\x85\xa5\xe6\x96\x87\xe6\x9c\xac\xe6\x88\x96\xe4\xb8\x8a\xe4\xbc\xa0\xe6\x96\x87\xe6\x9c\xac\xe6\x96\x87\xe4\xbb\xb6\'\n                    + \'</textarea>\'\n                + \'</td>\'\n                + \'<td>\'\n                    +\n            \'<input type="button" value="Go!" onclick="sub_text()" class="btn-circle"></input>\'\n                + \'</td>\'\n                + \'<td>\'\n                    + \'<textarea cols="100" rows="30"\'\n                        + \'class="form-control"\'\n                        + \'id="result_text"\'\n\n                        + \'name="result_text_name">\'\n\n                    + \'</textarea>\'\n                + \'</td>\'\n            + \'</tr>\'\n        + \'</table>\';\n        return html;\n    }\n    function blur_input_text()\n    {\n        text = document.getElementById("file_text");\n        if (text.value == ""){\n            text.value = "\xe5\x9c\xa8\xe6\xad\xa4\xe9\x94\xae\xe5\x85\xa5\xe6\x96\x87\xe6\x9c\xac\xe6\x88\x96\xe4\xb8\x8a\xe4\xbc\xa0\xe6\x96\x87\xe6\x9c\xac\xe6\x96\x87\xe4\xbb\xb6";\n        }\n    }\n    function focus_input_text(){\n        text = document.getElementById("file_text");\n        if (text.value == "\xe5\x9c\xa8\xe6\xad\xa4\xe9\x94\xae\xe5\x85\xa5\xe6\x96\x87\xe6\x9c\xac\xe6\x88\x96\xe4\xb8\x8a\xe4\xbc\xa0\xe6\x96\x87\xe6\x9c\xac\xe6\x96\x87\xe4\xbb\xb6"){\n            text.value = "";\n        }\n    }\n    function get_single_img_html() {\n        html = ""\n        + \'<p>\xe8\xaf\xb7\xe4\xb8\x8a\xe4\xbc\xa0\xe4\xb8\x80\xe4\xb8\xaa\xe5\x9b\xbe\xe7\x89\x87\xe6\x96\x87\xe4\xbb\xb6</p>\'\n        + \'<input type="file" id="file" onchange="handle_img(this.files)"/>\'\n        + \'<table class="table table-striped table-dark table-hover">\'\n            + \'<tr>\'\n                + \'<td style="width: 45%">\'\n                    + \'<img width="100%" id="file_img" name="input_img" value="kitten.jpg"/>\'\n                + \'</td>\'\n                + \'<td>\'\n                    + \'<input type="button" value="Start!" onclick="sub_img()"></input>\'\n                + \'</td>\'\n                + \'<td style="width: 45%"><table>\'\n                    + \'<tr><td>\'\n                        + \'<img width="100%" id="result_img" name="output_img"/>\'\n                    + \'</td></tr>\'\n                    + \'<tr><td>\'\n                        + \'<textarea cols="100" rows="2"\'\n                            + \'class="form-control"\'\n                            + \'id="result_text"\'\n                            + \'name="result_text_name">\'\n                        + \'</textarea>\'\n                    + \'</td></tr>\'\n                + \'</table></td>\'\n            + \'</tr>\'\n        + \'</table>\';\n        return html;\n    }\n    function select_category(module_categoty) {\n        select_module("Choose...");\n        option_html = get_module_option(module_categoty);\n        document.getElementById("inputGroupSelect02").innerHTML = option_html;\n    }\n    function select_module(module_name){\n        if (module_name == "Choose..."){\n            display_html = ""\n        }else{\n            if (document.getElementById("inputGroupSelect01").value == "nlp_module"){\n                display_html = get_single_text_html();\n            }else if (document.getElementById("inputGroupSelect01").value == "cv_module"){\n                display_html = get_single_img_html();\n            }\n\n        }\n        document.getElementById("display_div").innerHTML = display_html;\n    }\n    function handle_text(files) {\n        if (files.length){\n            let file = files[0];\n            let reader = new FileReader();\n            reader.onload = function(){\n                document.getElementById(\'file_text\').value = this.result;\n            };\n            reader.readAsText(file);\n        }\n    }\n    function handle_img(files) {\n        if (files.length){\n            let file = files[0];\n            let reader = new FileReader();\n            reader.onload = function(){\n                document.getElementById(\'file_img\').src = this.result;\n            };\n            reader.readAsDataURL(file);\n        }\n    }\n    function get_result_html(results) {\n        html = "";\n        for (var i=0, len=results.length; i<len; ++i){\n            html = html\n            + JSON.stringify(results[i])\n            + \'\\r\\n\'\n        }\n        return html;\n    }\n    function sub_text() {\n        var formParam = $("#main_form").serialize();\n        to_url = "/predict/text/" + document.getElementById("inputGroupSelect02").value;\n        $.ajax({\n                cache: true,\n                type: "POST",\n                url:to_url,\n                data:formParam,\n                async: false,\n                error: function(request) {\n                    alert("Connection error:"+request.error);\n                },\n                success: function(data) {\n                    console.log(data);\n                    html = get_result_html(data["results"]);\n                    document.getElementById("result_text").value = html;\n                }\n            });\n    }\n    function sub_img() {\n        var formParam = {\n            "image": document.getElementById("file_img").src,\n            "input_file":document.getElementById("file").value\n        };\n        to_url = "/predict/image/" + document.getElementById("inputGroupSelect02").value;\n        $.ajax({\n                cache: true,\n                type: "POST",\n                url:to_url,\n                data:formParam,\n                async: false,\n                error: function(request) {\n                    alert("Connection error:"+request.error);\n                },\n                success: function(data) {\n                    data = data.results;\n                    data = data.replace(/\'/g, \'"\');\n                    data = JSON.parse(data);\n                    data = data[0];\n\n                    document.getElementById("result_text").value = JSON.stringify(data.data[0]);\n                    document.getElementById("result_img").src = data.base64;\n                }\n            });\n    }\n</script>\n</body>\n</html>'
>>> 

Welcome to Ubuntu 19.04 (GNU/Linux 5.0.0-13-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue Jul 21 07:46:09 UTC 2020

  System load:  0.07               Processes:            215
  Usage of /:   32.2% of 18.57GB   Users logged in:      1
  Memory usage: 50%                IP address for ens33: 192.168.230.132
  Swap usage:   0%

 * "If you've been waiting for the perfect Kubernetes dev solution for
   macOS, the wait is over. Learn how to install Microk8s on macOS."

   https://www.techrepublic.com/article/how-to-install-microk8s-on-macos/

543 updates can be installed immediately.
0 of these updates are security updates.

Your Ubuntu release is not supported anymore.
For upgrade information, please visit:
http://www.ubuntu.com/releaseendoflife

New release '20.04 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Tue Jul 21 07:27:30 2020 from 192.168.230.1
Welcome to Ubuntu 19.04 (GNU/Linux 5.0.0-13-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue Jul 21 07:46:09 UTC 2020

  System load:  0.07               Processes:            215
  Usage of /:   32.2% of 18.57GB   Users logged in:      1
  Memory usage: 50%                IP address for ens33: 192.168.230.132
  Swap usage:   0%

 * "If you've been waiting for the perfect Kubernetes dev solution for
   macOS, the wait is over. Learn how to install Microk8s on macOS."

   https://www.techrepublic.com/article/how-to-install-microk8s-on-macos/

543 updates can be installed immediately.
0 of these updates are security updates.

Your Ubuntu release is not supported anymore.
For upgrade information, please visit:
http://www.ubuntu.com/releaseendoflife

New release '20.04 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Tue Jul 21 07:27:30 2020 from 192.168.230.1
z@z:~$ wget https://bkimg.cdn.bcebos.com/pic/86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5https://bkimg.cdn.bcebos.com/pic/86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5
The name is too long, 267 chars total.
Trying to shorten...
New name is 86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image%2Fwatermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5https:%2F%2Fbkimg.cdn.bcebos.com%2Fpic%2F86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image%2Fwatermark,image_d2F.
--2020-07-21 07:48:37--  https://bkimg.cdn.bcebos.com/pic/86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5https://bkimg.cdn.bcebos.com/pic/86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5
Resolving bkimg.cdn.bcebos.com (bkimg.cdn.bcebos.com)... 1.193.147.35, 240e:93c:2:3::2463:ae23
Connecting to bkimg.cdn.bcebos.com (bkimg.cdn.bcebos.com)|1.193.147.35|:443... connected.
HTTP request sent, awaiting response... 400 Bad Request
2020-07-21 07:48:45 ERROR 400: Bad Request.

z@z:~$ wget https://bkimg.cdn.bcebos.com/pic/86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5
--2020-07-21 07:48:55--  https://bkimg.cdn.bcebos.com/pic/86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5
Resolving bkimg.cdn.bcebos.com (bkimg.cdn.bcebos.com)... 1.193.147.35, 240e:93c:2:3::2463:ae23
Connecting to bkimg.cdn.bcebos.com (bkimg.cdn.bcebos.com)|1.193.147.35|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34329 (34K) [image/jpeg]
Saving to: ‘86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image%2Fwatermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5’

86d6277f9e2f0708f41a2dd5e324b 100%[=================================================>]  33.52K  --.-KB/s    in 0.006s

2020-07-21 07:48:55 (5.34 MB/s) - ‘86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image%2Fwatermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5’ saved [34329/34329]

z@z:~$ ls
 8047.zip
'86d6277f9e2f0708f41a2dd5e324b899a801f2cc?x-bce-process=image%2Fwatermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5'
 base64.py
 get-pip.py
 laji
 laji.py
z@z:~$ wget https://paddlehub.bj.bcebos.com/resources/test_img_cat.jpg
--2020-07-21 07:55:40--  https://paddlehub.bj.bcebos.com/resources/test_img_cat.jpg
Resolving paddlehub.bj.bcebos.com (paddlehub.bj.bcebos.com)... 220.181.33.43, 220.181.33.44
Connecting to paddlehub.bj.bcebos.com (paddlehub.bj.bcebos.com)|220.181.33.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 36914 (36K) [image/jpeg]
Saving to: ‘test_img_cat.jpg’

test_img_cat.jpg              100%[=================================================>]  36.05K  --.-KB/s    in 0.05s

2020-07-21 07:55:40 (692 KB/s) - ‘test_img_cat.jpg’ saved [36914/36914]

z@z:~$ wget https://paddlehub.bj.bcebos.com/resources/test_img_dog.jpg
--2020-07-21 07:57:23--  https://paddlehub.bj.bcebos.com/resources/test_img_dog.jpg
Resolving paddlehub.bj.bcebos.com (paddlehub.bj.bcebos.com)... 220.181.33.43, 220.181.33.44
Connecting to paddlehub.bj.bcebos.com (paddlehub.bj.bcebos.com)|220.181.33.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 113952 (111K) [image/jpeg]
Saving to: ‘test_img_dog.jpg’

test_img_dog.jpg              100%[=================================================>] 111.28K  --.-KB/s    in 0.1s

2020-07-21 07:57:23 (843 KB/s) - ‘test_img_dog.jpg’ saved [113952/113952]

z@z:~$ ifconfig
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.230.132  netmask 255.255.255.0  broadcast 192.168.230.255
        inet6 fe80::20c:29ff:fec7:46b5  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:c7:46:b5  txqueuelen 1000  (Ethernet)
        RX packets 380933  bytes 552710095 (552.7 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 81548  bytes 5525786 (5.5 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 220  bytes 19254 (19.2 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 220  bytes 19254 (19.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

z@z:~$ netstat -a
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0      0 localhost:domain        0.0.0.0:*               LISTEN
tcp        0      0 0.0.0.0:ssh             0.0.0.0:*               LISTEN
tcp        0      0 0.0.0.0:8866            0.0.0.0:*               LISTEN
tcp        0      0 z:41986                 api.snapcraft.io:https  ESTABLISHED
tcp        0      0 z:37774                 api.snapcraft.io:https  ESTABLISHED
tcp        0      0 z:37766                 api.snapcraft.io:https  ESTABLISHED
tcp        0      0 z:ssh                   192.168.230.1:56985     ESTABLISHED
tcp        0    208 z:ssh                   192.168.230.1:57458     ESTABLISHED
tcp        0      0 z:58762                 api.snapcraft.io:https  ESTABLISHED
tcp        0      0 z:42004                 api.snapcraft.io:https  ESTABLISHED
tcp6       0      0 [::]:ssh                [::]:*                  LISTEN
udp        0      0 localhost:domain        0.0.0.0:*
udp        0      0 z:bootpc                0.0.0.0:*
raw6       0      0 [::]:ipv6-icmp          [::]:*                  7
Active UNIX domain sockets (servers and established)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  2      [ ]         DGRAM                    37680    /run/user/1000/systemd/notify
unix  2      [ ACC ]     SEQPACKET  LISTENING     26690    /run/udev/control
unix  2      [ ACC ]     STREAM     LISTENING     37683    /run/user/1000/systemd/private
unix  2      [ ACC ]     STREAM     LISTENING     37689    /run/user/1000/gnupg/S.dirmngr
unix  2      [ ACC ]     STREAM     LISTENING     37690    /run/user/1000/gnupg/S.gpg-agent.extra
unix  2      [ ACC ]     STREAM     LISTENING     37691    /run/user/1000/gnupg/S.gpg-agent.browser
unix  2      [ ACC ]     STREAM     LISTENING     37692    /run/user/1000/gnupg/S.gpg-agent.ssh
unix  2      [ ACC ]     STREAM     LISTENING     37693    /run/user/1000/gnupg/S.gpg-agent
unix  2      [ ACC ]     STREAM     LISTENING     29198    @/org/kernel/linux/storage/multipathd
unix  2      [ ACC ]     STREAM     LISTENING     31871    /var/snap/lxd/common/lxd/unix.socket
unix  3      [ ]         DGRAM                    26655    /run/systemd/notify
unix  2      [ ACC ]     STREAM     LISTENING     26658    /run/systemd/private
unix  2      [ ACC ]     STREAM     LISTENING     26669    /run/lvm/lvmetad.socket
unix  2      [ ACC ]     STREAM     LISTENING     26673    /run/systemd/journal/stdout
unix  9      [ ]         DGRAM                    26675    /run/systemd/journal/socket
unix  8      [ ]         DGRAM                    26683    /run/systemd/journal/dev-log
unix  2      [ ]         DGRAM                    26688    /run/systemd/journal/syslog
unix  2      [ ACC ]     STREAM     LISTENING     26694    /run/lvm/lvmpolld.socket
unix  2      [ ACC ]     STREAM     LISTENING     30551    /var/run/vmware/guestServicePipe
unix  2      [ ACC ]     STREAM     LISTENING     31304    /run/snapd.socket
unix  2      [ ACC ]     STREAM     LISTENING     31306    /run/snapd-snap.socket
unix  2      [ ACC ]     STREAM     LISTENING     31868    /run/uuidd/request
unix  2      [ ACC ]     STREAM     LISTENING     31315    /var/run/dbus/system_bus_socket
unix  2      [ ACC ]     STREAM     LISTENING     31637    /var/run/irqbalance898.sock
unix  2      [ ACC ]     STREAM     LISTENING     31870    @ISCSIADM_ABSTRACT_NAMESPACE
unix  3      [ ]         STREAM     CONNECTED     32021
unix  3      [ ]         STREAM     CONNECTED     39977
unix  3      [ ]         DGRAM                    26657
unix  3      [ ]         STREAM     CONNECTED     34019
unix  3      [ ]         DGRAM                    31097
unix  3      [ ]         DGRAM                    37681
unix  3      [ ]         STREAM     CONNECTED     32562
unix  3      [ ]         DGRAM                    29653
unix  3      [ ]         STREAM     CONNECTED     32177
unix  3      [ ]         STREAM     CONNECTED     28184    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     39976
unix  3      [ ]         STREAM     CONNECTED     31411
unix  3      [ ]         STREAM     CONNECTED     31321
unix  3      [ ]         STREAM     CONNECTED     32182    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    26860
unix  3      [ ]         STREAM     CONNECTED     41926
unix  3      [ ]         STREAM     CONNECTED     28120
unix  3      [ ]         STREAM     CONNECTED     30117    /run/systemd/journal/stdout
unix  3      [ ]         DGRAM                    26656
unix  3      [ ]         STREAM     CONNECTED     30207
unix  3      [ ]         STREAM     CONNECTED     31709
unix  3      [ ]         DGRAM                    31095
unix  2      [ ]         DGRAM                    29648
unix  3      [ ]         STREAM     CONNECTED     30601    /run/systemd/journal/stdout
unix  3      [ ]         DGRAM                    29654
unix  3      [ ]         STREAM     CONNECTED     30867    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    27033
unix  3      [ ]         DGRAM                    37682
unix  3      [ ]         STREAM     CONNECTED     32558    /run/systemd/journal/stdout
unix  3      [ ]         DGRAM                    29651
unix  2      [ ]         DGRAM                    37658
unix  3      [ ]         STREAM     CONNECTED     32810
unix  3      [ ]         STREAM     CONNECTED     41925
unix  3      [ ]         STREAM     CONNECTED     29185    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     37684
unix  3      [ ]         STREAM     CONNECTED     27028    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     33194
unix  3      [ ]         STREAM     CONNECTED     30116
unix  3      [ ]         STREAM     CONNECTED     33045    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     33041    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     30689    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     32258    /run/systemd/journal/stdout
unix  3      [ ]         DGRAM                    31096
unix  3      [ ]         DGRAM                    29652
unix  3      [ ]         STREAM     CONNECTED     33044    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     32022    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     32559    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     28183
unix  3      [ ]         STREAM     CONNECTED     30686
unix  2      [ ]         DGRAM                    37645
unix  3      [ ]         STREAM     CONNECTED     32637
unix  3      [ ]         STREAM     CONNECTED     30403
unix  3      [ ]         DGRAM                    31094
unix  3      [ ]         STREAM     CONNECTED     40359    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     40358
unix  3      [ ]         STREAM     CONNECTED     32639    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     26957
unix  3      [ ]         STREAM     CONNECTED     37685    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     34080    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     31089
unix  3      [ ]         STREAM     CONNECTED     33038
unix  3      [ ]         DGRAM                    26477
unix  2      [ ]         STREAM     CONNECTED     39763
unix  3      [ ]         DGRAM                    26476
unix  2      [ ]         DGRAM                    30693
unix  2      [ ]         DGRAM                    39014
unix  2      [ ]         DGRAM                    30602
unix  3      [ ]         STREAM     CONNECTED     33442
unix  3      [ ]         STREAM     CONNECTED     33103
unix  3      [ ]         STREAM     CONNECTED     34196    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     33040    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     33220
unix  3      [ ]         STREAM     CONNECTED     33338
unix  3      [ ]         STREAM     CONNECTED     33221
unix  3      [ ]         STREAM     CONNECTED     33046    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     33820
unix  3      [ ]         STREAM     CONNECTED     31876
unix  3      [ ]         STREAM     CONNECTED     31877
unix  2      [ ]         STREAM     CONNECTED     38816
unix  2      [ ]         DGRAM                    33037
unix  3      [ ]         STREAM     CONNECTED     37632
unix  2      [ ]         DGRAM                    26474
unix  2      [ ]         DGRAM                    30404
unix  2      [ ]         DGRAM                    39812
unix  2      [ ]         DGRAM                    34008
unix  3      [ ]         STREAM     CONNECTED     33821    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    33082
unix  3      [ ]         STREAM     CONNECTED     33039
unix  3      [ ]         STREAM     CONNECTED     33443    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     33104    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     34201
unix  3      [ ]         STREAM     CONNECTED     34200
unix  2      [ ]         DGRAM                    37421
unix  3      [ ]         STREAM     CONNECTED     34026
unix  3      [ ]         STREAM     CONNECTED     33042    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     37633    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     29599    /run/systemd/journal/stdout
z@z:~$ python2.7
Python 2.7.18rc1 (default, Apr  7 2020, 12:05:55)
[GCC 9.3.0] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import requests
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/home/z/.local/lib/python2.7/site-packages/requests/__init__.py", line 43, in <module>
    import urllib3
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/__init__.py", line 7, in <module>
    from .connectionpool import HTTPConnectionPool, HTTPSConnectionPool, connection_from_url
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/connectionpool.py", line 11, in <module>
    from .exceptions import (
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/exceptions.py", line 2, in <module>
    from .packages.six.moves.http_client import IncompleteRead as httplib_IncompleteRead
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/packages/six.py", line 199, in load_module
    mod = mod._resolve()
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/packages/six.py", line 113, in _resolve
    return _import_module(self.mod)
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/packages/six.py", line 82, in _import_module
    __import__(name)
  File "/usr/lib/python2.7/httplib.py", line 1270, in <module>
    import ssl
  File "/usr/lib/python2.7/ssl.py", line 146, in <module>
    import base64        # for DER-to-PEM translation
  File "base64.py", line 2
    '
    ^
SyntaxError: EOL while scanning string literal
>>> import json
>>> import 64
  File "<stdin>", line 1
    import 64
            ^
SyntaxError: invalid syntax
>>> import base64
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "base64.py", line 2
    '
    ^
SyntaxError: EOL while scanning string literal
>>> exit()
z@z:~$ pip install requests -i https://mirror.baidu.com/pypi/simple
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Defaulting to user installation because normal site-packages is not writeable
Looking in indexes: https://mirror.baidu.com/pypi/simple
Requirement already satisfied: requests in ./.local/lib/python2.7/site-packages (2.24.0)
Requirement already satisfied: urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 in ./.local/lib/python2.7/site-packages (from requests) (1.25.9)
Requirement already satisfied: certifi>=2017.4.17 in ./.local/lib/python2.7/site-packages (from requests) (2020.6.20)
Requirement already satisfied: chardet<4,>=3.0.2 in ./.local/lib/python2.7/site-packages (from requests) (3.0.4)
Requirement already satisfied: idna<3,>=2.5 in ./.local/lib/python2.7/site-packages (from requests) (2.10)
z@z:~$ pip install base64 -i https://mirror.baidu.com/pypi/simple
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Defaulting to user installation because normal site-packages is not writeable
Looking in indexes: https://mirror.baidu.com/pypi/simple
ERROR: Could not find a version that satisfies the requirement base64 (from versions: none)
ERROR: No matching distribution found for base64
z@z:~$ python2.7
Python 2.7.18rc1 (default, Apr  7 2020, 12:05:55)
[GCC 9.3.0] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import numpy as np

data = ["test_img_dog.jpg"]
label_map = dataset.label_dict()
index = 0
# get classification result
run_states = task.predict(data=data)
results = [run_state.run_results for run_state in run_states]

for batch_result in results:
    # get prTraceback (most recent call last):
e  File "<stdin>", line 1, in <module>
d  File "/home/z/.local/lib/python2.7/site-packages/numpy/__init__.py", line 142, in <module>
    ifrom . import core
  File "/home/z/.local/lib/python2.7/site-packages/numpy/core/__init__.py", line 40, in <module>
c    from . import multiarray
  File "/home/z/.local/lib/python2.7/site-packages/numpy/core/multiarray.py", line 12, in <module>
t index
        from . import overrides
  File "/home/z/.local/lib/python2.7/site-packages/numpy/core/overrides.py", line 8, in <module>
bat    from numpy.compat._inspect import getargspec
  File "/home/z/.local/lib/python2.7/site-packages/numpy/compat/__init__.py", line 14, in <module>
    from . import py3k
  File "/home/z/.local/lib/python2.7/site-packages/numpy/compat/py3k.py", line 15, in <module>
    from pathlib import Path, PurePath
  File "/home/z/.local/lib/python2.7/site-packages/pathlib.py", line 16, in <module>
    from urllib import quote as urlquote, quote as urlquote_from_bytes
  File "/usr/lib/python2.7/urllib.py", line 30, in <module>
ch_result     import base64
  File "base64.py", line 2
    '
    ^
SyntaxError: EOL while scanning string literal
>>>
>>> data = ["test_img_dog.jpg"]
>>> label_map = dataset.label_dict()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'dataset' is not defined
>>> index = 0
>>> # get classification result
... run_states = task.predict(data=data)
Traceback (most recent call last):= np
  File "<stdin>", line 2, in <module>
NameError: name 'task' is not defined
>>> results = [run_state.run_results for run_state in run_states]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'run_states' is not defined
>>>
>>> for batch_result in results:
...     # get predict index
...     batch_result = np.argmax(batch_result, axis=2)[0]
...     for result in batch_result:
...         index += 1
...         result = label_map[result]
...         print("input %i is %s, and the predict result is %s" %
...               (index, data[index - 1], result))
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'results' is not defined
>>> import requests
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/home/z/.local/lib/python2.7/site-packages/requests/__init__.py", line 43, in <module>
    import urllib3
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/__init__.py", line 7, in <module>
    from .connectionpool import HTTPConnectionPool, HTTPSConnectionPool, connection_from_url
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/connectionpool.py", line 11, in <module>
    from .exceptions import (
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/exceptions.py", line 2, in <module>
    from .packages.six.moves.http_client import IncompleteRead as httplib_IncompleteRead
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/packages/six.py", line 199, in load_module
    mod = mod._resolve()
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/packages/six.py", line 113, in _resolve
    return _import_module(self.mod)
  File "/home/z/.local/lib/python2.7/site-packages/urllib3/packages/six.py", line 82, in _import_module
    __import__(name)
  File "/usr/lib/python2.7/httplib.py", line 1270, in <module>
    import ssl
  File "/usr/lib/python2.7/ssl.py", line 146, in <module>
    import base64        # for DER-to-PEM translation
  File "base64.py", line 2
    '
    ^
SyntaxError: EOL while scanning string literal
>>> exit()
z@z:~$ pip install urllib3 -i https://mirror.baidu.com/pypi/simple
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Defaulting to user installation because normal site-packages is not writeable
Looking in indexes: https://mirror.baidu.com/pypi/simple
Requirement already satisfied: urllib3 in ./.local/lib/python2.7/site-packages (1.25.9)
z@z:~$ pip install ssl -i https://mirror.baidu.com/pypi/simple
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Defaulting to user installation because normal site-packages is not writeable
Looking in indexes: https://mirror.baidu.com/pypi/simple
Collecting ssl
  Downloading https://mirror.baidu.com/pypi/packages/83/21/f469c9923235f8c36d5fd5334ed11e2681abad7e0032c5aba964dcaf9bbb/ssl-1.16.tar.gz (33 kB)
    ERROR: Command errored out with exit status 1:
     command: /usr/bin/python2.7 -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-AVRmVy/ssl/setup.py'"'"'; __file__='"'"'/tmp/pip-install-AVRmVy/ssl/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base /tmp/pip-pip-egg-info-UzHxHo
         cwd: /tmp/pip-install-AVRmVy/ssl/
    Complete output (5 lines):
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
      File "/tmp/pip-install-AVRmVy/ssl/setup.py", line 12, in <module>
        + "or earlier.")
    ValueError: This extension should not be used with Python 2.6 or later (already built in), and has not been tested with Python 2.3.4 or earlier.
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
z@z:~$ pip install ssl
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Defaulting to user installation because normal site-packages is not writeable
Collecting ssl
  Downloading ssl-1.16.tar.gz (33 kB)
    ERROR: Command errored out with exit status 1:
     command: /usr/bin/python2.7 -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-bIpdNC/ssl/setup.py'"'"'; __file__='"'"'/tmp/pip-install-bIpdNC/ssl/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base /tmp/pip-pip-egg-info-qpdQut
         cwd: /tmp/pip-install-bIpdNC/ssl/
    Complete output (5 lines):
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
      File "/tmp/pip-install-bIpdNC/ssl/setup.py", line 12, in <module>
        + "or earlier.")
    ValueError: This extension should not be used with Python 2.6 or later (already built in), and has not been tested with Python 2.3.4 or earlier.
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
z@z:~$ yum install openssl-devel

Command 'yum' not found, did you mean:

  command 'uum' from deb freewnn-jserver (1.1.1~a021+cvs20130302-7build1)
  command 'num' from deb quickcal (2.4-1)
  command 'sum' from deb coreutils (8.30-3ubuntu2)
  command 'zum' from deb perforate (1.2-5.1)

Try: sudo apt install <deb name>

z@z:~$ sudo apt install openssl-devel
[sudo] password for z:
正在读取软件包列表... 完成
正在分析软件包的依赖关系树
正在读取状态信息... 完成
E: 无法定位软件包 openssl-devel
z@z:~$ apt-get install libssl-dev
E: 无法打开锁文件 /var/lib/dpkg/lock-frontend - open (13: Permission denied)
E: 无法获取 dpkg 前端锁 (/var/lib/dpkg/lock-frontend)，请查看您是否正以 root 用户运行？
z@z:~$ sudo apt-get install libssl-dev
正在读取软件包列表... 完成
正在分析软件包的依赖关系树
正在读取状态信息... 完成
将会同时安装下列软件：
  libssl1.1
建议安装：
  libssl-doc
下列【新】软件包将被安装：
  libssl-dev
下列软件包将被升级：
  libssl1.1
升级了 1 个软件包，新安装了 1 个软件包，要卸载 0 个软件包，有 430 个软件包未被升级。
需要下载 2,900 kB 的归档。
解压缩后会消耗 8,082 kB 的额外空间。
您希望继续执行吗？ [Y/n] y
获取:1 http://mirrors.aliyun.com/ubuntu focal/main amd64 libssl1.1 amd64 1.1.1f-1ubuntu2 [1,318 kB]
获取:2 http://mirrors.aliyun.com/ubuntu focal/main amd64 libssl-dev amd64 1.1.1f-1ubuntu2 [1,582 kB]
已下载 2,900 kB，耗时 1秒 (2,316 kB/s)
正在预设定软件包 ...
(正在读取数据库 ... 系统当前共安装有 68314 个文件和目录。)
准备解压 .../libssl1.1_1.1.1f-1ubuntu2_amd64.deb  ...
正在解压 libssl1.1:amd64 (1.1.1f-1ubuntu2) 并覆盖 (1.1.1b-1ubuntu2) ...
正在选中未选择的软件包 libssl-dev:amd64。
准备解压 .../libssl-dev_1.1.1f-1ubuntu2_amd64.deb  ...
正在解压 libssl-dev:amd64 (1.1.1f-1ubuntu2) ...
正在设置 libssl1.1:amd64 (1.1.1f-1ubuntu2) ...
正在设置 libssl-dev:amd64 (1.1.1f-1ubuntu2) ...
正在处理用于 libc-bin (2.31-0ubuntu9) 的触发器 ...
z@z:~$vmware蓝屏 另一个程序已锁定文件的一部分，进程无法访问  
打不开磁盘“E:\Ubuntu\Ubuntu 64 位.vmdk”或它所依赖的某个快照磁盘。  
模块“Disk”启动失败。  
未能启动虚拟机。

排查原因：删除 lck 后缀的文件夹（保护文件）



