=====================================================|
MDC010 - TRABALHO FINAL - IDENTIFICAÇÃO DE EMPRESAS  |
GRUPO G14                                            |
=====================================================|

----------------------------|
MINIMO PARA RODAR O CODIGO  |
----------------------------|

Todo o código do trabalho encontra-se no Notebook enviado, que foi criado e executado no Google Colab.
Esse Notebook foi separado em seções numeradas. Sempre que fizermos referência à 'seção X', isso refere-se a uma seção do Notebook.

Após aberto o Notebook, favor executar as seções abaixo:
- Parte 0   (atalho no Google Drive)
- Parte 1
  - seção 1.1 (Bibliotecas e Google Drive)
  - seção 1.2 (Funções Auxiliares usadas ao longo do código)
  - seção 1.5 (Copiando arquivos do drive para pasta 'local')


=====================================================|
MAIS DETALHES SOBRE O NOTEBOOK E OS DADOS UTILIZADOS |
=====================================================|



----------------------------|
SOBRE OS DADOS              |
----------------------------|

O trabalho utiliza dois tipos de dados:

- Imagens:
    Treino Original: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//train
    Treino Aumentado: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//train_aumentado
    Validação: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//val
    Teste: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//test

- Arquivos CVS:
    Treino: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//random_forest//dados_tabulares_com_CEP__TRAIN.csv
    Validação: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//random_forest//dados_tabulares_com_CEP__VAL.csv
    Teste: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//random_forest//dados_tabulares_com_CEP__TEST.csv
    

A seção 1.4 explica a sepração dos dados, e contém informações do link de compartilhamento para os dados usados.
        
----------------------------|
AMBIENTE DE EXECUÇÃO        |
----------------------------|

O Notebook foi criado e executado no Google Colab, de forma que o código sempre referencia caminhos relativos
a esse ambiente. Exemplos:

//content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//split_train_val_test//train
//content//treino

-------------------------------------------------------|
EXECUÇÃO DE CÉLULAS PARA ACELERAR TEMPO DE TREINAMENTO |
-------------------------------------------------------|

Local no Notebook: "PARTE 1: Preparação do Ambiente e Separação dos Dados" -> "1.5) Copiando arquivos do drive 'localmente' para acelerar o treino"

O que faz: A execução das células desse bloco copia os dados (do Google Drive Compartilhado) para a estrutura de diretórios da máquina local
afim de que o treinamento ocorra de maneira mais rápida. 

Sua execução criará a seguinte estrutura de pastas:

Imagens de Treino Original: //content//train
Imagens de Treino Aumentado: //content//train_aumentado
Imagens de Validação: //content/val
Imagens de Test: //content/test

A seção "1.5 - Copiando arquivos do drive 'localmente' para acelerar o treino"  contém o código que faz essa cópia.

----------------------------|
FUNÇÕES AUXILIARES          |
----------------------------|
O notebook contém algumas funções auxiliares que são utilizadas por todo o código, de forma que precisam ser
executadas antes do treinamento das redes e avaliação dos resultados.

São duas células a serem executadas na Seção 1.2


------------------------------|
MODELOS USANDO IMAGENS        |
------------------------------|

Foram treinadas diversas redes utilizando imagens. Esse treinamento ocorre ao longo da Seção 2.0
São diversas redes com variações de números de épocas, conjunto de treinamento, otimizadores e regularizadores.
Abaixo estão destacados três grupos: baseline (importante para efeitos de comparação) e as duas redes
eleitas para compor a solução final, um ensemble de três modelos.


**BASELINE**

Seção de treinamento: 2.1.3
Local onde está salva: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//Redes_Treinadas//Congeladas//resnet50_congelada_seed42.rede


**REDES DO MODELO FINAL**
São duas as CNN's que compõe o modelo final:


*VGG19
Seção de treinamento: 2.9.8
Local onde está salva: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//Redes_Treinadas//Functional//VGG19//Seed42//vgg19_adam_l2_0001_balanced.rede

*Xception:
Seção de treinamento: 2.3.1.4
Local onde está salva: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//Redes_Treinadas//xception_functional.rede


 
---------------------------------|
MODELOS USANDO DADOS TABULARES   |
---------------------------------|

Foi treinada uma Random Forest a partir dos dados tabulares.

Para efetuar o treinamento, a seção 3.1.1 deve ser executada primeiro.

Seção de treinamento: 3.1.2
Local onde está salva: //content//drive//MyDrive//INF0619_G14_Dados_Empresas_Fantasmas//Redes_Treinadas//randomforest.rede


----------------------------|
ENSEMBLE E SOLUÇÃO FINAL    |
----------------------------|

- ENSEMBLE 'VENCEDOR': Seção 4.2.6


-----------------------------|
RESUMO DOS RESULTADOS FINAIS |
-----------------------------|

- Seção 5.1


----------------------------------------------------|
EXECUÇÃO DOS MAPAS DE ATIVAÇÃO E 'TREE INTERPRETER' |
----------------------------------------------------|

- Seção 6.3

