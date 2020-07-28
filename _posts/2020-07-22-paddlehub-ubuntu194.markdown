---
layout: post
title:  "paddlehub-ubuntu194"
date:   2020-07-21 13:19:48 +0800
categories: python

---
# paddlehub-ubuntu194 #

启动vmware
hub serving start -m vgg11_imagenet

客户端：
Python 2.7.18 (v2.7.18:8d21aa21f2, Apr 20 2020, 13:25:05) [MSC v.1500 64 bit (AMD64)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> import requests
>>> import json
>>> files = [("image", (open("H:\\bushudog\\test_img_cat.jpg", "rb")))]
>>> url = "http://192.168.230.132:8866/predict/image/vgg11_imagenet"
>>> r = requests.post(url=url, files=files)
>>> results = eval(r.json()["results"])
>>> print(json.dumps(results, indent=4, ensure_ascii=False))
[
    [
        {
            "Egyptian cat": 0.7822089791297913
        }
    ]
]
>>> results
[[{'Egyptian cat': 0.7822089791297913}]]
>>> 

安装 hub serving start -m mobilenet_v2_imagenet

!pip install paddlehub==1.6.2 -i https://pypi.tuna.tsinghua.edu.cn/simple

import paddlehub as hub

module = hub.Module(name="mobilenet_v2_imagenet")

dataset = hub.dataset.DogCat()

data_reader = hub.reader.ImageClassificationReader(
    image_width=module.get_expected_image_width(),
    image_height=module.get_expected_image_height(),
    images_mean=module.get_pretrained_images_mean(),
    images_std=module.get_pretrained_images_std(),
    dataset=dataset)
	
config = hub.RunConfig(
    use_cuda=False,
    num_epoch=1,
    checkpoint_dir="cv_finetune_turtorial_demo",
    batch_size=32,
    eval_interval=50,
    strategy=hub.finetune.strategy.DefaultFinetuneStrategy())
	
报错---------------------------------------------------------------------------AttributeError                            Traceback (most recent call last)<ipython-input-18-d33e491dedad> in <module>
      4     feature=feature_map,
      5     num_classes=dataset.num_labels,
----> 6     config=config)
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddlehub/finetune/task/classifier_task.py in __init__(self, feature, num_classes, feed_list, data_reader, startup_program, config, hidden_units, metrics_choices)
     47             startup_program=startup_program,
     48             config=config,
---> 49             metrics_choices=metrics_choices)
     50 
     51         self.feature = feature
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddlehub/finetune/task/base_task.py in __init__(self, feed_list, data_reader, main_program, startup_program, config, metrics_choices)
    297         else:
    298             self._base_main_program = clone_program(
--> 299                 main_program, for_test=False)
    300         if startup_program is None:
    301             self._base_startup_program = clone_program(
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddlehub/common/paddle_helper.py in clone_program(origin_program, for_test)
    272     dest_program = fluid.Program()
    273     _copy_vars_and_ops_in_blocks(origin_program.global_block(),
--> 274                                  dest_program.global_block())
    275     dest_program = dest_program.clone(for_test=for_test)
    276     if not for_test:
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddlehub/common/paddle_helper.py in _copy_vars_and_ops_in_blocks(from_block, to_block)
    145     for var in from_block.vars:
    146         var = from_block.var(var)
--> 147         var_info = copy.deepcopy(get_variable_info(var))
    148         if isinstance(var, fluid.framework.Parameter):
    149             to_block.create_parameter(**var_info)
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddlehub/common/paddle_helper.py in get_variable_info(var)
     63         var_info['optimize_attr'] = var.optimize_attr
     64         var_info['regularizer'] = var.regularizer
---> 65         var_info['gradient_clip_attr'] = var.gradient_clip_attr
     66         var_info['do_model_average'] = var.do_model_average
     67     else:
AttributeError: 'Parameter' object has no attribute 'gradient_clip_attr'

排查错误：vi /opt/conda/envs/python27-paddle120-env/lib/python2.7/site-packages/paddlehub/common/paddle_helper.py
vi /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddlehub/common/paddle_helper.py

添加
import paddle
from paddlehub.common.utils import from_pyobj_to_module_attr, from_module_attr_to_pyobj, version_compare

修改66行
if not version_compare(paddle.__version__, '1.8'):
            var_info['gradient_clip_attr'] = var.gradient_clip_attr
			
报错完美解决。
			
			





