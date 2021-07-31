### Integração Zabbix <-> Grafana ###

Uma das integrações mais comuns com o Zabbix é com o Grafana, que basicamente é utilizado para exibir em forma de dashboards (painéis), aquilo que é obtido no monitoramento realizado pelo Zabbix. Esta integração ocorre através de um plugin do tipo App, que traz também  um datasource (pois o Grafana possui plugins do tipo App, Datasources e Panels), que você instala no server Grafana e o configura com parâmetros de acordo com seu ambiente e isto possibilita que o Grafana enxergue os dados e os exiba da forma que for desejada.

![image](https://user-images.githubusercontent.com/41125728/127752151-af74b032-1765-478a-9558-5090093333e6.png)

O plugin foi desenvolvido por Alexander Zobnin, e sua instalação é super tranquila, pois, após instalado o Grafana, com apenas uma linha de comando, você instala o plugin, reinicializa o Grafana Server e depois ativa e o configura para conectar-se ao seu Zabbix.

**Licenças**
  * Do Grafana: AGPLv3
  * Do plugin Zabbix-Grafana: Apache 2.0.

### Instale o Grafana ###

Para instalar o Grafana, verifique a plataforma a qual designará para ser seu Grafana Server e siga as instruções no link abaixo (não estou levando em conta que você irá utilizar os serviços de Cloud da Grafana Labs, mas sim, o modo Self Managed):
  * Instalação do Grafana: https://grafana.com/grafana/download?pg=get&plcmt=selfmanaged-box1-cta1 e https://grafana.com/docs/grafana/latest/installation/
  * Depois de instalado, verifique a documentação para guiá-lo com as configurações pós-instalação: https://grafana.com/docs/grafana/latest/

### Ok, Grafana instalado, agora eu quero integrá-lo ao meu Zabbix! ###
Nesta etapa, você já tem seu grafana-server instalado e irá realizar a instalação do plugin via _grafana-cli_, seguindo inicialmente as instruções abaixo:
* Visão Geral: https://grafana.com/grafana/plugins/alexanderzobnin-zabbix-app/
* Install do plugin: https://grafana.com/grafana/plugins/alexanderzobnin-zabbix-app/?tab=installation

* Documentação direta de configuração e administração do plugin Zabbix-Grafana e o GitHub:
  * https://alexanderzobnin.github.io/grafana-zabbix/
  * https://github.com/alexanderzobnin/grafana-zabbix

* Informação sobre a CLI do Grafana (caso interesse explorar):
  * https://grafana.com/docs/grafana/latest/administration/cli/#plugins-commands

### Importante! ###

Depois de instalado, é necessário **ativar o plugin**. Para isso, faça o seguinte:
  * Vá até a aba **Apps** do Grafana, na seção de **Plugins**;
  * Acesse a aba **Config**;
  * Leia o que houver de avisos e demais infos e depois clique em **Enable**
  * Alguns dashboards vem inclusos e aparecem na lateral direita, clique em importar para fazer uso dos mesmos (pode ser necessário modificar algumas coisas que possam estar sem funcionar/pegar dados),
  * Configure seu datasource apontando para o Zabbix.

Pronto, já está apto para iniciar o desenvolvimento de seus dashboards exibindo infos do seu Zabbix! :)
