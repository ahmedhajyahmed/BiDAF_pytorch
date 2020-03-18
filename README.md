# BiDAF_pytorch
Implementing the Bidirectional Attention Flow model using pytorch

0. configure your environment:

        - create a conda env : conda create {"env name"} python= 3.5
        - activate {"env name"}
        - install all requirements 


1. preprocessing your dataset : 

        - run  python setup.py
                * this will preprocess SQuAD 2.0 traing , dev , test and my_test datasets ( dataset containing a concrete example) 
                * this will also dowlnlods the Glove 300-dimensional word vectors
        

2. train your model : 

        - create "save" folder
        - run python train.py --name training 
                * this will train your model by reading command line arguments, loading SQuAD dataset
                * you can add --num_epochs argument to specify the number of epochs 
                * with 10 epochs you will have : F1: 58.47 , EM: 55.42 , AvNA: 64.88
        
 
3. to test your model with the dev/test SQUAD dataset: 

        - run python test.py --name dev/test --split dev/test --load_path ./save/{"your training folder"}/best.pth.tar

4. to visualize the machine learning workflow in tensorboard :

        - run tensorboard --logdir ./save/{"your training folder"}

        
5. to test your model with your test dataset

        - run python my_test.py -name test --split test  --load_path ./save/{"your training folder"}/best.pth.tar
        
