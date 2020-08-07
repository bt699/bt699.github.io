---
layout: post
title:  "paddleclas"
date:   2020-07-28 13:19:48 +0800
categories: python

---
# paddleclas #
git clone https://github.com/PaddlePaddle/PaddleClas.git

unzip PaddleClas-master.zip

cd PaddleClas-master

pip install --upgrade -r requirements.txt

tar -xf /home/aistudio/data/data31417/flowers102.tar -C dataset/

在终端下：
export PYTHONPATH=$PWD:$PYTHONPATH
python -m paddle.distributed.launch \
    --selected_gpus="0" \
    tools/train.py \
        -c ./configs/quick_start/ResNet50_vd.yaml
		
预训练模型地址
[](https://paddleclas.readthedocs.io/zh_CN/latest/models/models_intro.html#id4)

python tools/download.py -a ResNet50_vd -p ./pretrained -d True

[](https://paddle-imagenet-models-name.bj.bcebos.com/ResNet50_vc_pretrained.tar)

export PYTHONPATH=$PWD:$PYTHONPATH
python -m paddle.distributed.launch \
    --selected_gpus="0" \
    tools/train.py \
        -c ./configs/quick_start/ResNet50_vd_finetune.yaml
		
		
		
下载预训练模型	ResNet50_vd_ssld
python tools/download.py -a ResNet50_vd_ssld -p ./pretrained -d True



export PYTHONPATH=$PWD:$PYTHONPATH
python -m paddle.distributed.launch \
    --selected_gpus="0" \
    tools/train.py \
        -c ./configs/quick_start/ResNet50_vd_ssld_finetune.yaml
		
		
数据增广
export PYTHONPATH=$PWD:$PYTHONPATH
python -m paddle.distributed.launch \
    --selected_gpus="0" \
    tools/train.py \
        -c ./configs/quick_start/ResNet50_vd_ssld_random_erasing_finetune.yaml
		



cp -r output/ResNet50_vd/19/ ./pretrained/flowers102_R50_vd_final/


python tools/download.py -a MobileNetV3_large_x1_0 -p ./pretrained -d True

SSLD知识蒸馏
export PYTHONPATH=$PWD:$PYTHONPATH
python -m paddle.distributed.launch \
    --selected_gpus="0" \
    tools/train.py \
        -c ./configs/quick_start/R50_vd_distill_MV3_large_x1_0.yaml
		
export PYTHONPATH=$PWD:$PYTHONPATH		
python tools/eval.py \
    -c ./configs/eval.yaml \
    -o ARCHITECTURE.name="ResNet50_vd" \
    -o pretrained_model=output/ResNet50_vd/best_model/ppcls	
		
		
python -m paddle.distributed.launch \
    --selected_gpus="0" \
    tools/eval.py \
    -c ./configs/eval.yaml \
    -o ARCHITECTURE.name="ResNet50_vd" \
    -o pretrained_model=output/ResNet50_vd/19/ppcls
	
	export PYTHONPATH=$PWD:$PYTHONPATH
	python -m paddle.distributed.launch \
	    --selected_gpus="0" \
	    tools/eval.py \
	    -c ./configs/eval.yaml \
	    -o ARCHITECTURE.name="ResNet50_vd" \
	    -o pretrained_model=output/ResNet50_vd/19/ppcls
	
	
cp -r ./pretrained/ ./pretrained_model


