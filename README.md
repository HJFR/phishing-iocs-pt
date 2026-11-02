# HJFR — IOCs de phishing (Portugal)

Indicadores de compromisso de campanhas de phishing analisadas pela HJFR em Portugal.
**TLP:CLEAR** · Licença **CC BY 4.0** (atribuição: «HJFR — hjfr-info.pt») · Atualizado: 2026-10-31

| Ficheiro | Conteúdo | Ação |
|---|---|---|
| `feeds/url-block.txt` | **URLs completos** dos e-mails (forma original + IPv4 normalizada) — IOC principal | **Bloquear** (proxy, filtro web, gateway de correio) |
| `feeds/ip-review.txt` | IPs de destino dos links (IPv4 + IPv6 mapeado) | **Alertar**; bloquear só depois de confirmar que o IP não aloja serviços legítimos |
| `feeds/domain-block.txt` | Domínios/subdomínios usados só pelo phishing (nunca serviços partilhados) | **Bloquear** (DNS, proxy) |
| `feeds/email-sender-block.txt` | Remetentes | Quarentena / bloquear |
| `feeds/sha256.txt` | SHA-256 dos ficheiros de e-mail (`.eml`/`.msg`) | Pesquisa / EDR |
| `feeds/phone-alert.txt` | Números de telefone de phishing por chamada (faturas falsas) | **Alertar** (helpdesk, sensibilização) |
| `feeds/patterns.txt` | Regex de assunto e URL | Alertar |
| `feeds/ip-context-report-only.txt` | Servidores de alojamento por onde os e-mails foram enviados (segundo os cabeçalhos) | **Não bloquear às cegas** |
| `iocs.csv` | Todos os indicadores com confiança, ação, datas e campanha | — |
| `stix/*.json` | Bundle STIX 2.1 | MISP / OpenCTI |

**Campanhas:** `PT-BANK-DATAUPDATE-2026-10` (28–29/10/2026) — e-mails «Atualização dos dados» a imitar a CGD («Caixa Empresas»)
e o Millennium bcp («Millennium Private»); links para IPs escritos como IPv6 mapeado (217.60.237.162 / .104).
Outras campanhas (e-mails analisados um a um, 02/11/2026; páginas de destino já inativas nessa data):

| Campanha | Período | Marca imitada | Truque observado |
|---|---|---|---|
| `PT-BANCOCTT-2026-10` | 12/10/2026 | Banco CTT | encurtador tr.ee → subdomínio de alojamento |
| `PT-PAYPAL-2026-10` | 26/10/2026 | PayPal | remetente falsificado; encurtador tr.ee → subdomínio de alojamento |
| `PT-AT-FATURA-2026-05` | 18/05/2026 | Autoridade Tributária (Fatura Eletrónica) | link com «utilizador@» enganador |
| `FR-KLARNA-2026-05` | 09/05/2026 | Klarna | código QR dinâmico como redirecionador |
| `FR-DECATHLON-2026-05` | 22/05/2026 | Decathlon | endereço IP escrito em octal |
| `DE-DISNEYPLUS-2026-06` | 07/06/2026 | Disney+ | serviços de envio em massa; página em armazenamento na nuvem |
| `WEBROOT-CALLBACK-2026-06` | 01/06/2026 | Webroot | recibo falso com número de telefone |

As marcas citadas foram imitadas nas mensagens e não têm responsabilidade nelas.

**Nota:** os indicadores descrevem o que a HJFR observou nas mensagens analisadas, nas datas indicadas. A presença de um
servidor, endereço ou fornecedor nesta lista identifica infraestrutura técnica observada; não significa que o fornecedor ou o
titular tenham participado ou tido conhecimento.

Correções: https://www.hjfr-info.pt/contacto · Disponibilizado «tal como está», sem garantias.

Bloquear pelo URL completo é preciso e não afeta outros sites que partilhem o mesmo IP; bloquear um IP inteiro pode cortar
o acesso a serviços legítimos.

*EN: Phishing IOCs observed in Portugal by HJFR (TLP:CLEAR, CC BY 4.0). Block the full URLs (`url-block.txt`) and senders;
alert on `ip-review.txt` and block those IPs only after confirming they host nothing legitimate; alert on `patterns.txt`;
do not block `ip-context-report-only.txt` (hosting servers on the sending path). Listing infrastructure does not imply
responsibility or knowledge of its providers or holders.*
