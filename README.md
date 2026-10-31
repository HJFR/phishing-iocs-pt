# HJFR — IOCs de phishing (Portugal)

Indicadores de compromisso de campanhas de phishing analisadas pela HJFR em Portugal.
**TLP:CLEAR** · Licença **CC BY 4.0** (atribuição: «HJFR — hjfr-info.pt») · Atualizado: 2026-10-31

| Ficheiro | Conteúdo | Ação |
|---|---|---|
| `feeds/url-block.txt` | **URLs completos** dos e-mails (forma original + IPv4 normalizada) — IOC principal | **Bloquear** (proxy, filtro web, gateway de correio) |
| `feeds/ip-review.txt` | IPs dos servidores das páginas falsas (IPv4 + IPv6 mapeado) | **Alertar**; bloquear só depois de confirmar que o IP não aloja serviços legítimos |
| `feeds/email-sender-block.txt` | Remetentes | Quarentena / bloquear |
| `feeds/sha256.txt` | SHA-256 dos `.eml` | Pesquisa / EDR |
| `feeds/patterns.txt` | Regex de assunto e URL | Alertar |
| `feeds/ip-context-report-only.txt` | Alojamento partilhado que retransmitiu os e-mails | **Não bloquear às cegas** |
| `iocs.csv` | Todos os indicadores com confiança, ação, datas e campanha | — |
| `stix/*.json` | Bundle STIX 2.1 | MISP / OpenCTI |

**Campanhas:** `PT-BANK-DATAUPDATE-2026-10` (28–29/10/2026) — e-mails «Atualização dos dados» a imitar a CGD («Caixa Empresas»)
e o Millennium bcp («Millennium Private»); links para IPs escritos como IPv6 mapeado (217.60.237.162 / .104).
As marcas foram imitadas pelos atacantes e não têm responsabilidade nestas campanhas.

Falsos positivos: https://www.hjfr-info.pt/contacto · Disponibilizado «tal como está», sem garantias.

Bloquear pelo URL completo é preciso e não afeta outros sites que partilhem o mesmo IP; bloquear um IP inteiro pode cortar
o acesso a serviços legítimos.

*EN: Phishing IOCs observed in Portugal by HJFR (TLP:CLEAR, CC BY 4.0). Block the full URLs (`url-block.txt`) and senders;
alert on `ip-review.txt` and block those IPs only after confirming they host nothing legitimate; alert on `patterns.txt`;
do not block `ip-context-report-only.txt` (shared hosting relays).*
