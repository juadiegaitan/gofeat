# GO FEAT

[GO FEAT](http://computationalbiology.ufpa.br/gofeat/) is a free, online, user friendly platform for functional annotation and enrichment of genomic and transcriptomic data based on homology search analysis. GO FEAT overcomes the limitations of current tools by allowing users to generate reports, tables, GO charts and graphs that help the user with downstream analysis of data. In addition, GO FEAT allow users to export the results with different output formats.

### Instalation

In order to run GO FEAT in your local web server, you need to perform these steps:
1. Clone GO FEAT project into your web server's document root directory:
```
git clone https://github.com/fabriciopa/gofeat
```

2. Create a MYSQL database and import the [gofeat.sql](http://computationalbiology.ufpa.br/gofeat/gofeat.sql.tar.gz) file to it.

3. Configure the 'gofeat/application/configs/application.ini' file for the database (lines 13-19) and DIAMOND (lines 22-32) usage;

Database parameters you need to change:
```
resources.multidb.name1.dbname = YOUR_DATABASE_NAME
resources.multidb.name1.username = YOUR_DATABASE_USERNAME
resources.multidb.name1.password = "YOUR_DATABASE_PASSWORD"
resources.multidb.name1.host = "YOUR_DATABASE_SERVER"
```
DIAMOND parameters you need to change:
```
diamond.emailEbi = "YOUR_EMAIL"
diamond.useDiamond = "true_or_false"
diamond.nSeqs = "number_of_seqs_before_use_diamond (integer)"
diamond.remoteDiamond = "true (in case you want to run the diamond in another server)"
diamond.nCore =  "number_of_cores_for_diamond (integer)"
diamond.remoteHost = "remote_ip_diamond_server"
diamond.remotePort = "remote_port_diamond_server"
diamond.remoteUser = "remote_user_diamond_server"
diamond.remotePwd = "remote_password_diamond_server"
diamond.workDir = "diamond_work_directory (remote or local)"
diamond.uniprotkb = "diamond_uniprotkb_database_directory (remote or local)"
```
3. Start the bots to check if any new sequence needs to be annotated:
```
nohup wget -O bot http://YOUR_WEB_SERVER/gofeat/index/botblast &
```
If you are using DIAMOND, also start the DIAMOND bot:
```
nohup wget -O bot http://YOUR_WEB_SERVER/gofeat/index/botdiamond &
```

## Authors
* **Fabricio Araujo** - *Universidade Federal do Pará, Instituto de Ciências Biológicas* - [GOFEAT](http://computationalbiology.ufpa.br/gofeat/)
* **Debmalya Barh** - *Centre for Genomics and Applied Gene Technology, Institute of Integrative Omics and Applied Biotechnology´*
* **Artur Silva** - *Universidade Federal do Pará, Instituto de Ciências Biológicas*
* **Luis Guimarães** - *Universidade Federal do Pará, Instituto de Ciências Biológicas*
* **Rommel Thiago Jucá Ramos** - *Universidade Federal do Pará, Instituto de Ciências Biológicas*

Use araujopa@gmail.com or rommelthiago@gmail.com for comments and questions.

## License
This project is licensed under the MIT License.
