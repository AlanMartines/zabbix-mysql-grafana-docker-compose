<h1>Zabbix & Grafana Docker Compose</h1>

<p>Este repositório contém um arquivo <code>docker-compose.yml</code> para a implantação do Zabbix (incluindo frontend, servidor, banco de dados e agent) e Grafana.</p>
<blockquote>
    Utilizadas as imagens oficiais do Zabbix, do Grafana e do MySQL. Os links para consulta estão no final deste artigo.
</blockquote>
<h2>Pré-requisitos</h2>

<ul>
    <li>Docker instalado</li>
    <li>Docker Compose instalado</li>
</ul>

<h2>Configuração</h2>

<ol>
    <li>Clone este repositório:
        <pre><code>git clone https://github.com/AlanMartines/zabbix-docker-compose.git
cd zabbix-docker-compose</code></pre>
    </li>
</ol>

<h2>Implantação</h2>

<p>Para iniciar os serviços:</p>
<pre><code>docker-compose up -d</code></pre>

<p>Para parar os serviços:</p>
<pre><code>docker-compose down</code></pre>

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

<h2>Contribuições</h2>

<p><a href="CONTRIBUTING.md">Contribuições</a> são bem-vindas! Por favor, abra uma issue ou pull request.</p>

<h2>Licença</h2>

<p>
    Este projeto está sob a licença MIT. Veja o arquivo <a href="LICENSE">LICENSE</a> para mais detalhes.
</p>
