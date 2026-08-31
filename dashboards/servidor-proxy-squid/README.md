# Dashboard : Servidor Proxy Squid

Dashboard do Splunk para controlo e monitorização de um servidor proxy Squid. Os dados vêm do ficheiro `/var/log/squid/access.log`, e o dashboard tem um seletor de servidor (host) no topo para filtrar os resultados.

## O que monitora

- **Métodos HTTP perigosos (TRACE / TRACK):** lista todas as requisições HTTP com método, URI, utilizador, estado e agente, para identificar o uso de métodos potencialmente perigosos.
- **Conexões CONNECT para portas não seguras:** deteta ligações em túnel (CONNECT) para portas fora do permitido, classificando cada tentativa como sucesso, bloqueada, falha de autenticação ou host inacessível.
- **Fuga de metadados e topologia de rede:** identifica tentativas de reconhecimento (pedidos HEAD, consultas a serviços externos de verificação de IP) e assinala quando os cabeçalhos de resposta (Via, Server, X-Cache) expõem informação interna da rede.
- **Evasão por domínio / lista negra:** mostra os acessos bloqueados (403/DENIED), distinguindo entre padrões de URL maliciosos conhecidos e domínios em lista negra.
- **Conexões simultâneas por origem:** gráfico do volume de requisições por IP de origem ao longo do tempo, para identificar possível exaustão de recursos ou ataques de negação de serviço.

## Ficheiros

- [conf.xml](conf.xml) — definição do dashboard em XML (Splunk Simple XML).
