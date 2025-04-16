<p align="center">
    <img src="technology-two.png" width="200" alt="Logo" />
</p>

<h1>Zabbix & Grafana Docker Compose</h1>

<p>Este repositório contém um arquivo <code>docker-compose.yml</code> para a implantação do Zabbix (incluindo frontend, servidor, banco de dados e agent) e Grafana.</p>
<blockquote>
    Utilizadas as imagens oficiais do Zabbix, do Grafana e do MySQL. Os links para consulta estão no final deste artigo.
</blockquote>

<h2>Pré-requisitos</h2>

<p>Antes de começar a usar este projeto, certifique-se de ter os seguintes pré-requisitos instalados em sua máquina:</p>

<ul>
    <li><b>Docker:</b> A plataforma Docker é necessária para criar e gerenciar os containers do projeto. <a href="https://docs.docker.com/get-docker/">Instale o Docker aqui</a>.</li>
    <li><b>Docker Compose:</b> Ferramenta para definir e executar aplicações Docker de vários containers. <a href="https://docs.docker.com/compose/install/">Instale o Docker Compose aqui</a>.</li>
    <li><b>Git:</b> Sistema de controle de versão necessário para clonar o repositório. <a href="https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git">Instale o Git aqui</a>.</li>
</ul>

<p>Após instalar os pré-requisitos acima, você pode seguir as instruções de instalação e uso.</p>

<h2>Configuração</h2>

<ol>
    <li>Clone este repositório:
        <pre><code>git clone https://github.com/AlanMartines/zabbix-docker-compose.git
cd zabbix-docker-compose</code></pre>
    </li>
    <li>Configuração inicial:
        <pre><code>cp .env-example .env</code></pre>
    </li>
    <li>Criando os volumes:
        <pre><code>mkdir -p /usr/local/docker/</code></pre>
    </li>
    <li>Aplicando permições:
        <pre><code>chmod -R 777 /usr/local/docker/*</code></pre>
    </li>
    <li>Habitar o swarm (Opicional):
        <pre><code>docker swarm init</code></pre>
    </li>
</ol>

<h2>Implantação Frontend</h2>

<p>Para iniciar os serviços:</p>
<pre><code>docker compose -f docker-compose-monitor.yml up --build -d --no-recreate</code></pre>

<h2>Serviços Incluídos</h2>

<ul>
    <li><strong>zabbix-mysql</strong>: Banco de dados MySQL para Zabbix.</li>
    <li><strong>zabbix-snmptraps</strong>: Serviço SNMP Traps para Zabbix.</li>
    <li><strong>zabbix-server</strong>: Servidor Zabbix.</li>
    <li><strong>zabbix-frontend</strong>: Frontend do Zabbix usando Nginx.</li>
    <li><strong>zabbix-agent</strong>: Agente Zabbix.</li>
    <li><strong>zabbix-grafana</strong>: Grafana com o plugin Zabbix.</li>
</ul>

<h2>Links para as Imagens Oficiais</h2>

<ul>
    <li><strong>Mysql:</strong> <a href="https://hub.docker.com/_/mysql" target="_blank">https://hub.docker.com/_/mysql</a></li>
    <li><strong>Zabbix:</strong> <a href="https://hub.docker.com/u/zabbix" target="_blank">https://hub.docker.com/u/zabbix</a></li>
    <li><strong>Grafana:</strong> <a href="https://hub.docker.com/u/grafana" target="_blank">https://hub.docker.com/u/grafana</a></li>
</ul>

<h2>Implantação Backend</h2>

<p>Para iniciar os serviços:</p>
<pre><code>docker compose -f docker-compose-backend.yml up --build -d --no-recreate</code></pre>

<h2>Serviços Incluídos</h2>

<ul>
    <li><strong>prometheus</strong>: O Prometheus é um sistema de monitoramento e alerta.</li>
    <li><strong>node-exporter</strong>: O Node Exporter é um exportador para métricas de hardware e do sistema operacional.</li>
    <li><strong>alert-manager</strong>: O Alertmanager gerencia alertas para o Prometheus.</li>
    <li><strong>cadvisor</strong>: O cAdvisor (Container Advisor) fornece análise de desempenho e uso de recursos para containers em execução.</li>
    <li><strong>netdata</strong>: Netdata é uma ferramenta de monitoramento em tempo real que oferece insights sobre métricas de performance.</li>
    <li><strong>nginx-prometheus-exporter</strong>: Nginx Prometheus Exporter torna possível monitorar o NGINX ou NGINX Plus usando o Prometheus.</li>
</ul>

<h2>Links para as Imagens Oficiais</h2>

<ul>
    <li><strong>Prometheus:</strong> <a href="https://hub.docker.com/r/prom/prometheus" target="_blank">https://hub.docker.com/r/prom/prometheus</a></li>
    <li><strong>Node Exporter:</strong> <a href="https://hub.docker.com/r/prom/node-exporter" target="_blank">https://hub.docker.com/r/prom/node-exporter</a></li>
    <li><strong>Alertmanager:</strong> <a href="https://hub.docker.com/r/prom/alertmanager" target="_blank">https://hub.docker.com/r/prom/alertmanager</a></li>
    <li><strong>cAdvisor:</strong> <a href="https://hub.docker.com/r/google/cadvisor" target="_blank">https://hub.docker.com/r/google/cadvisor</a></li>
    <li><strong>Netdata:</strong> <a href="https://hub.docker.com/r/netdata/netdata" target="_blank">https://hub.docker.com/r/netdata/netdata</a</li>
    <li><strong>Nginx Prometheus Exporter:</strong> <a href="https://hub.docker.com/r/nginx/nginx-prometheus-exporter/" target="_blank">https://hub.docker.com/r/nginx/nginx-prometheus-exporter/</a</li>
</ul>

<h1>Nota</h1>
<h2>Instalação de Dependências após a criação do container zabbix-server (Ubuntu)</h2>
<pre>
<code>
docker exec -it -u root zabbix-server /bin/bash
apt update; \
apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget; \
apt install -y python3 python3-pip whois; \
rm /usr/lib/python*/EXTERNALLY-MANAGED;

cd ~; \
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb; \
apt-get install -y ./google-chrome-stable_current_amd64.deb; \
google-chrome --version;
</code>
</pre>

<h2>Dependências</h2>
<pre>
<code>
pip3 install bs4; \
pip3 install requests; \
pip3 install cloudscraper; \
pip3 install cfscrape; \
pip3 install requests six; \
pip3 install beautifulsoup4==4.9.0; \
pip3 install certifi==2020.4.5.1; \
pip3 install chardet==3.0.4; \
pip3 install cloudscraper==1.2.33; \
pip3 install idna==2.9; \
pip3 install requests-toolbelt==0.9.1; \
pip3 install soupsieve==2.0; \
pip3 install urllib3==1.25.9; \
pip3 install --upgrade urllib3 chardet requests; \
pip3 install selenium; \
pip3 install webdriver-manager; \
pip3 install --upgrade urllib3 chardet requests;
</code>
</pre>

<h2>Expose Basic Nginx Metrics</h2>
<pre>
<code>
vim /etc/nginx/conf.d/status.conf
</code>
</pre>

<h2>nginx/status.conf</h2>
<pre>
<code>
server {
	listen 127.0.0.1:80;
	server_name 127.0.0.1;
	location /nginx_status {
		stub_status on;
		access_log off;
		allow 127.0.0.1;
		deny all;
	}
}
</code>
</pre>

<h2>Restarting Nginx</h2>
<pre>
<code>
nginx -t
systemctl reload nginx
</code>
</pre>


<h2>Contribuições</h2>

<p><a href="CONTRIBUTING.md">Contribuições</a> são bem-vindas! Por favor, abra uma issue ou pull request.</p>

<h2>Licença</h2>

<p>
    Este projeto está sob a licença MIT. Veja o arquivo <a href="LICENSE">LICENSE</a> para mais detalhes.
</p>
