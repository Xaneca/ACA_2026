# ACA organization

Para ACA organizei umas ideia para fazer a MLP, e podemos reproduzir na CNN e ResNet
DATASET -> Train / VAL -> train.augment() -> Early Stop + Timer -> train

- Early stop para evitar overfit
- Timer para calcular eficiencia
- Guardar acc e loss de train e val a cada epoch num csv para cada teste. E depois a partir dos csv é q fazemos graficos. Assim se pensarmos em graficos no futuro, n temos de correr de novo as coisas
    - escrever nos csv so no final de cada treino -> fica mais rapido
- Escolha de Hiperparametros: Learning Rate -> Loss Function -> Optimizer -> Hidden Size

Talvez na CNN e ResNet é preciso adicionar mais hiperparametros, mas para a MLP parece me suficiente

# TODO

- [ ] MLP
- [ ] CNN
- [ ] ResNet

## MLP

- [ ] Add early stop
- [ ] Add timer (Efficiency)
- [ ] Save results
    - [ ] in order to rpesent tables with all trainand val accuracy and loss, for each test
    - [ ] Save train and Val acc and Loss ate each epoch
        - in this way we can then do various graphics from these data
- [ ] Baseline
- [ ] Best Learning Rate [0.1, 0.01, 0.001, 0.0001]
- [ ] Best Loss [Cross Entropy, Multi Margin Loss, ...]
- [ ] Best Optimizer [Adam, SGD, RMSprop]
- [ ] Best Hidden Layer Size

# Folders

/aca-butterflies 
    /train
    /test
/Results
    /MLP
        /learning_rate.csv
            /lr_0_1
                lr_0_1.pth
                lr_0_1.csv      -> HEADER: epoch, train_acc, val_acc, train_loss, val_loss, timer
            /lr_0_0_1
                lr_0_0_1.pth
                lr_0_0_1.csv
            /lr_0_0_0_1
                lr_0_0_0_1.pth
                lr_0_0_0_1.csv
            /lr_0_0_0_0_1
                lr_0_0_0_0_1.pth
                lr_0_0_0_0_1.csv
        /loss_function
            model
            loss_function.csv   -> HEADER: epoch, train_acc, val_acc, train_loss, val_loss, timer
        /optimizer
            optimizer.csv       -> HEADER: epoch, train_acc, val_acc, train_loss, val_loss, timer
        /hidden_size
            hidden_size.csv     -> HEADER: epoch, train_acc, val_acc, train_loss, val_loss, timer
    /CNN
    /ResNet
mlp_code.ipynb          # train models
mlp_make_graphs.ipynb   # graphs and tables
cnn_code.ipynb
resnet_code.ipynb

# References:

- Early Stop: https://medium.com/@piyushkashyap045/early-stopping-in-deep-learning-a-simple-guide-to-prevent-overfitting-1073f56b493e

- Deep Learning Tuning Playbook: 
    - Initial configuration - starting point:
        (1) - Hidden Layer Size - 128
        (2) - Optimizer - Adam
        (3) - Loss Function - Cross Entropy
        (4) - Learning Rate - 0.001