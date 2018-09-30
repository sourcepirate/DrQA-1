Dawnbench instructions
====================

1) Use Amazon Deep Learning AMI (Ubuntu) Version 15.0 - ami-0b43cec40e1390f34

2) Configure Drive for 100GB of space + SSD

2) Install pytorch 0.4.1 w/ CUDA:

    conda install pytorch torchvision cuda92 -c pytorch

Clone git repo:

    git clone https://github.com/brettkoonce/DrQA

Original repo: https://github.com/hitvoice/DrQA.git

Checkout dawn_logging branch:

	cd DrQA
	git checkout dawn_logging

Follow readme:

    pip install -r requirements.txt

    bash download.sh

    python prepro.py

    python train.py -e 40 -bs 128 --save_last_only --save_dawn_logs

Technically, the p3 can support larger batch sizes, but convergence decreases, so use this size.

Then, use the following to generate the .csv entry for Dawnbench:

    grep dawn_entry models/log.txt | cut -c 32- > models/dawn_entry.csv