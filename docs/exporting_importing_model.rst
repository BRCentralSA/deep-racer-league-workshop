************************************************
04. Exportando e Importando seu modelo
************************************************

Nessa etapa do Workshop aprenderemos como exportar e importar nosso modelo no console DeepRacer.

Exportando seu Modelo
----------------------

É necessário que os arquivos sigam a seguinte estruturas de diretórios no S3

.. image:: _static/import_export/bucket_structure.png

Será necessário inicialmente exportar o seu moelo do DeepRacer para um bucket S3, acesse o console do DeepRacer vá em **Your Models**

.. image:: _static/import_export/console01.png

Selecione o modelo que quer exportar e clique em **Actions > Copy to S3**

.. image:: _static/import_export/console02.png

Em **S3 bucket** Selecione o bucket do DeepRacer já criado pelo próprio serviço, em **S3 object prefix (optional)** de um nome pra sua pasta onde sera armazenado o arquivo será exportado

.. image:: _static/import_export/console03.png

Clique em **Copy**

Agora aguarmadamente apoximadamente 1 minuto para copiar

.. image:: _static/import_export/console04.png

Download dos arquivos do S3
----------------------------

Será necessário o **aws-cli** devidamente configurado na sua máquina com as credenciais parar acessar o Bucket

Como configurar aws-cli - https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-chap-configure.html

Vá até o bucket que você exportou o seu modelo e copie o S3 URI

.. image:: _static/import_export/console05.png

No meu caso **s3://aws-deepracer-xxxxx-xxxx-xxxx/exportando_modelo/**

Abra o seu terminal com as credenciais configuradas

Crie uma pasta para fazer download dos seus modelos

Siga os passos abaixo

**mkdir meu_modelo_exportado**

**cd meu_modelo_exportado**

**aws s3 cp -r aws s3 cp --recursive s3://aws-deepracer-xxxxx-xxxxx-xxxxx/exportando_modelo/ ./**

.. image:: _static/import_export/terminal01.png

Após finalizdo o seu modelo já estará em sua máquina local e você pode re-importalo no console do DeepRacer

Importando Seu Modelo
---------------------- 

Exportando Seu Modelo Físico
-----------------------------