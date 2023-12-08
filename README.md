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
    <li><strong>rocketchat</strong>: Rocket.Chat.</li>
</ul>

<h2>Links para as Imagens Oficiais</h2>

<ul>
    <li><strong>Mysql:</strong> <a href="https://hub.docker.com/_/mysql" target="_blank">https://hub.docker.com/_/mysql</a></li>
    <li><strong>Zabbix:</strong> <a href="https://hub.docker.com/u/zabbix" target="_blank">https://hub.docker.com/u/zabbix</a></li>
    <li><strong>Grafana:</strong> <a href="https://hub.docker.com/u/grafana" target="_blank">https://hub.docker.com/u/grafana</a></li>
    <li><strong>Rocket.Chat:</strong> <a href="https://hub.docker.com/r/rocketchat/rocket.chat" target="_blank">https://hub.docker.com/r/rocketchat/rocket.chat</a></li>
</ul>

<h2>Implantação Backend</h2>

<p>Para iniciar os serviços:</p>
<pre><code>docker compose -f docker-compose-backend.yml up --build -d --no-recreate</code></pre>

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
