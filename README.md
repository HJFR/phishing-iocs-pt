# HJFR — IOCs de phishing (Portugal)

Indicadores de compromisso de campanhas de phishing analisadas pela HJFR em Portugal.
**TLP:CLEAR** · Licença **CC BY 4.0** (atribuição: «HJFR — hjfr-info.pt») · Atualizado: 2026-10-31

| Ficheiro | Conteúdo | Ação |
|---|---|---|
| `feeds/ip-block.txt` | IPs da infraestrutura de phishing (IPv4 + IPv6 mapeado) | Bloquear |
| `feeds/url-block.txt` | URLs dos e-mails (forma original + IPv4 normalizada) | Bloquear |
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

*EN: Phishing IOCs observed in Portugal by HJFR (TLP:CLEAR, CC BY 4.0). Block `*-block.txt`; alert on `patterns.txt`;
do not blindly block `ip-context-report-only.txt` (shared hosting relays).*
