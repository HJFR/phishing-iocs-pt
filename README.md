# HJFR — IOCs de phishing (Portugal)

Listas de indicadores de phishing observados pela HJFR. **Um indicador por linha, sem comentários**, prontas para importar
em firewalls, proxies, DNS, gateways de correio e SIEM.
**TLP:CLEAR** · Licença **CC BY 4.0** (atribuição: «HJFR — hjfr-info.pt»)

| Ficheiro | Conteúdo | Ação |
|---|---|---|
| `feeds/url-block.txt` | URLs completos (indicador principal) | Bloquear (proxy, filtro web, gateway de correio) |
| `feeds/domain-block.txt` | Domínios/subdomínios usados só pelo phishing | Bloquear (DNS, proxy) |
| `feeds/email-sender-block.txt` | Remetentes | Quarentena / bloquear |
| `feeds/ip-review.txt` | IPs de destino dos links | Alertar; bloquear só depois de confirmar que o IP não aloja serviços legítimos |
| `feeds/ip-context-report-only.txt` | Servidores de alojamento por onde os e-mails foram enviados | Não bloquear às cegas |
| `feeds/sha256.txt` | SHA-256 dos ficheiros de e-mail | Pesquisa / EDR |
| `feeds/phone-alert.txt` | Números de telefone de phishing por chamada (E.164) | Alertar |
| `feeds/url-patterns.txt` | Expressões regulares para URLs | Alertar |
| `feeds/email-sender-patterns.txt` | Expressões regulares para remetentes | Alertar |
| `feeds/subject-patterns.txt` | Expressões regulares para assuntos | Alertar |

Bloquear o URL completo é preciso e não afeta outros sites no mesmo IP. Encurtadores, serviços de QR, serviços de envio em
massa e armazenamento na nuvem nunca entram como domínio — só os URLs exatos.

Os indicadores descrevem o que a HJFR observou nas mensagens analisadas. A presença de um servidor, endereço ou fornecedor
nestas listas identifica infraestrutura técnica observada; não significa que o fornecedor ou o titular tenham participado ou
tido conhecimento. As marcas imitadas não têm responsabilidade nas mensagens. Dados das vítimas nunca são publicados.

Análises: https://www.hjfr-info.pt · Correções: https://www.hjfr-info.pt/contacto · Disponibilizado «tal como está», sem garantias.
