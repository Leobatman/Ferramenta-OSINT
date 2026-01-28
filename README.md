# OSINT Mega Suite 

<div align="center">

![Leonardo OSINT Suite](https://img.shields.io/badge/Leonardo-OSINT%20Suite-blue)
![Version](https://img.shields.io/badge/version-5.0.0-green)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-GPL--3.0-orange)
![Lines](https://img.shields.io/badge/lines-45%2B%20thousands-red)

**Uma ferramenta de inteligência de fontes abertas abrangente e expansiva**


<img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExbm55OTk1MXE1bWJrZmxnZ3lqZnVpbDAweDRqcWlhNWFuZ2N1MjJmeiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/hun4DFmfnDId3lid5b/giphy.gif">


</div>

## 🌟 **Visão Geral**

A **Leonardo Pereira OSINT Mega Suite** é uma ferramenta de inteligência de fontes abertas (OSINT) profissional e abrangente, projetada para pesquisadores de segurança, analistas de inteligência e profissionais de investigação digital. Com mais de 45.000 linhas de código, esta suíte oferece uma plataforma unificada para coleta, análise e correlação de informações de fontes públicas.

## ✨ **Recursos Principais**

### 🔍 **Módulos de Investigação**
- **Análise de Redes Sociais** (Twitter, Instagram, Facebook, LinkedIn, GitHub, etc.)
- **Inteligência de Domínios** (WHOIS, DNS, subdomínios, SSL, portas)
- **Inteligência de Emails** (validação, reputação, verificação de vazamentos)
- **Análise de Imagens** (metadados EXIF, busca reversa, detecção facial)
- **Inteligência de Telefones** (operadoras, localização)
- **Geolocalização** (IP, coordenadas, mapas)
- **Análise Blockchain** (criptomoedas, transações)
- **Threat Intelligence** (integração com VT, Shodan, Censys)

### 🛠️ **Sistema Avançado**
- **Gerenciador de Módulos** (carregamento dinâmico, instalação/atualização)
- **Sistema de Configuração** (múltiplos backends: JSON, YAML, SQLite, etc.)
- **Logging Profissional** (níveis customizados, auditoria, segurança)
- **Banco de Dados Integrado** (SQLite com histórico de execuções)
- **Gerador de Relatórios** (HTML, PDF, JSON, CSV, Markdown)
- **Interface CLI Avançada** (menus interativos, cores ANSI)

### 🔧 **Integrações**
- **70+ APIs** (Shodan, VirusTotal, Censys, HaveIBeenPwned, etc.)
- **50+ Bibliotecas Python** (requests, selenium, beautifulsoup4, etc.)
- **Frameworks de ML** (Torch, TensorFlow, Transformers)
- **Banco de Dados** (Elasticsearch, MongoDB, Redis, SQLAlchemy)

## 📋 **Pré-requisitos**

### **Sistema**
- Python 3.8 ou superior
- 4GB RAM mínimo (8GB recomendado)
- 2GB espaço em disco
- Conexão internet (para APIs e scraping)

### **Dependências Principais**
```bash
# Instalação básica
pip install requests beautifulsoup4 pandas numpy

# Para recursos avançados
pip install selenium pillow cryptography dnspython whois

# Para análise de imagens
pip install opencv-python tensorflow torch

# Para relatórios PDF
pip install reportlab
```

## 🚀 **Instalação Rápida**

### **Método 1: Clone do Repositório**
```bash
# Clone o repositório
git clone https://github.com/leonardopereira/osint-suite.git
cd osint-suite

# Instale dependências
pip install -r requirements.txt

# Execute a suíte
python leonardo_osint.py
```

### **Método 2: Instalação via Pip (Em breve)**
```bash
pip install leonardo-osint-suite
leonardo-osint
```

## 📖 **Uso Básico**

### **Inicialização**
```python
from leonardo_osint import LeonardoOSINTApp

# Inicialize a aplicação
app = LeonardoOSINTApp()
app.run()
```

### **Interface de Linha de Comando**
```bash
# Executar investigação completa
python leonardo_osint.py --target example.com --type domain

# Executar módulo específico
python leonardo_osint.py --module social_media --target "@username"

# Gerar relatório
python leonardo_osint.py --target victim@email.com --report html
```

### **Exemplos de Uso**

#### **1. Investigação de Domínio**
```python
from leonardo_osint import LeonardoOSINTApp

app = LeonardoOSINTApp()
result = app.investigate_domain("example.com", 
                                 analyses=['whois', 'dns', 'subdomains', 'ssl'])

# Exportar resultados
app.export_results(result, format='html', filename='domain_report.html')
```

#### **2. Análise de Email**
```python
result = app.analyze_email("user@example.com",
                            checks=['format', 'disposable', 'breaches', 'reputation'])

# Verificar vazamentos
if result['breach_count'] > 0:
    print(f"Email encontrado em {result['breach_count']} vazamentos!")
```

#### **3. Análise de Imagem**
```python
# Análise de metadados EXIF
result = app.analyze_image("photo.jpg",
                           analyses=['metadata', 'reverse_search', 'face_detection'])

# Extrair localização GPS
if 'gps' in result['metadata']:
    print(f"Localização: {result['metadata']['gps']['coordinates']}")
```

## 🏗️ **Arquitetura do Sistema**

### **Estrutura de Diretórios**
```
leonardo_osint_suite/
├── modules/                    # Módulos OSINT
│   ├── social_media/
│   ├── domain_intel/
│   ├── email_intel/
│   └── image_analysis/
├── config/
│   ├── config.ini             # Configurações principais
│   ├── api_keys.json          # Chaves de API
│   └── templates/             # Templates de relatório
├── database/
│   └── leonardo_osint.db      # Banco de dados SQLite
├── logs/                      # Logs do sistema
├── cache/                     # Cache de resultados
├── reports/                   # Relatórios gerados
└── backups/                   # Backups automáticos
```

### **Fluxo de Trabalho**
1. **Configuração**: Carregamento de configurações e APIs
2. **Carregamento de Módulos**: Inicialização dinâmica de módulos
3. **Execução**: Processamento paralelo de investigações
4. **Análise**: Correlação e enriquecimento de dados
5. **Relatório**: Geração de relatórios em múltiplos formatos
6. **Armazenamento**: Persistência em banco de dados

## 🔧 **Configuração**

### **Arquivo de Configuração (`config.ini`)**
```ini
[General]
version = 5.0.0
author = Leonardo Pereira
language = en
timezone = UTC

[Network]
timeout = 30
max_retries = 3
user_agent_rotation = true
rate_limit_delay = 1.0

[API_Keys]
shodan_api_key = SUA_CHAVE_AQUI
virustotal_api_key = SUA_CHAVE_AQUI
censys_api_id = SEU_ID_AQUI
censys_api_secret = SEU_SECRET_AQUI
```

### **Configurando APIs**
```python
from leonardo_osint import LeonardoConfig

config = LeonardoConfig()
config.set('API_Keys', 'shodan_api_key', 'sua_chave_shodan')
config.set('API_Keys', 'virustotal_api_key', 'sua_chave_virustotal')
config.save()
```

## 📊 **Módulos Disponíveis**

### **Módulos Principais**
| Módulo | Descrição | Status |
|--------|-----------|--------|
| `SocialMediaModule` | Análise de 15+ redes sociais | ✅ |
| `DomainIntelModule` | Inteligência completa de domínios | ✅ |
| `EmailIntelModule` | Validação e análise de emails | ✅ |
| `ImageAnalysisModule` | Análise forense de imagens | ✅ |
| `PhoneIntelModule` | Inteligência de números de telefone | 🚧 |
| `ThreatIntelModule` | Threat Intelligence integrado | ✅ |
| `BlockchainModule` | Análise de criptomoedas | 🚧 |

### **Módulos de Suporte**
| Módulo | Descrição |
|--------|-----------|
| `ReportGenerator` | Geração de relatórios multi-formato |
| `DataVisualizer` | Visualização de dados e gráficos |
| `AutomationEngine` | Automação de workflows OSINT |
| `APIManager` | Gerenciamento unificado de APIs |

## 📈 **Exemplos de Saída**

### **Saída JSON**
```json
{
  "investigation": {
    "target": "example.com",
    "timestamp": "2024-01-29T10:30:00Z",
    "modules_executed": ["whois", "dns", "subdomains"],
    "results": [
      {
        "type": "domain_whois",
        "data": {
          "registrar": "GoDaddy",
          "creation_date": "1997-03-15",
          "expiration_date": "2025-03-14"
        },
        "confidence": 0.95
      }
    ]
  }
}
```

## 🛡️ **Considerações Legais e Éticas**

### **Aviso Legal**
```text
Esta ferramenta deve ser usada APENAS para:
1. Pesquisas autorizadas
2. Testes de penetração com permissão
3. Investigação de segurança pessoal
4. Auditorias legais
5. Pesquisas acadêmicas

É PROIBIDO o uso para:
1. Atividades ilegais
2. Invasão de privacidade sem consentimento
3. Coleta de dados sem autorização
4. Violação de termos de serviço
```

### **Diretrizes Éticas**
1. Sempre obtenha permissão antes de testar sistemas
2. Respeite a privacidade dos indivíduos
3. Não cause danos ou interrupções
4. Reporte vulnerabilidades responsavelmente
5. Cumpra todas as leis aplicáveis

## 🤝 **Contribuindo**

### **Reportando Bugs**
1. Verifique se o bug já foi reportado nas [Issues](https://github.com/leonardopereira/osint-suite/issues)
2. Use o template de bug report
3. Inclua logs, screenshots e steps para reproduzir

### **Sugerindo Melhorias**
1. Abra uma issue com tag `enhancement`
2. Descreva a feature proposta
3. Explique o caso de uso

### **Desenvolvendo Módulos**
```python
from leonardo_osint.modules import BaseModule

class MeuNovoModulo(BaseModule):
    """Template para novos módulos"""
    
    def initialize(self):
        # Inicialização do módulo
        pass
    
    def execute(self, target, options=None):
        # Lógica principal
        pass
    
    def cleanup(self):
        # Limpeza de recursos
        pass
```


## 📄 **Licença**

Este projeto está licenciado sob a **GNU General Public License v3.0** - veja o arquivo [LICENSE](LICENSE) para detalhes.

```
Leonardo Pereira OSINT Mega Suite v5.0
Copyright (C) 2024 Leonardo Pereira

Este programa é software livre: você pode redistribuí-lo e/ou modificar
sob os termos da GNU General Public License conforme publicada por
a Free Software Foundation, seja versão 3 da Licença, ou
(à sua escolha) qualquer versão posterior.
```

### **Projetos Inspiradores**
- [theHarvester](https://github.com/laramies/theHarvester)
- [Recon-ng](https://github.com/lanmaster53/recon-ng)
- [SpiderFoot](https://github.com/smicallef/spiderfoot)
- [Maltego](https://www.maltego.com/)

### **APIs e Serviços**
- [Shodan](https://www.shodan.io/)
- [VirusTotal](https://www.virustotal.com/)
- [HaveIBeenPwned](https://haveibeenpwned.com/)
- [Censys](https://censys.io/)


### **FAQ**
**Q: A ferramenta é gratuita?**  
R: Sim, completamente open-source sob licença GPL-3.0.

**Q: Posso usar comercialmente?**  
R: Sim, desde que cumpra os termos da licença.

**Q: Preciso de conhecimento técnico?**  
R: A interface CLI é amigável, mas conhecimento básico de OSINT é recomendado.

**Q: É legal usar esta ferramenta?**  
R: Sim, para propósitos legítimos e autorizados.

---

<div align="center">

**Desenvolvido com ❤️ por Leonardo Pereira**


*"Conhecimento é poder, mas ética é responsabilidade"*

</div>

---

**Nota**: Esta ferramenta é fornecida "como está", sem garantias de qualquer tipo. O usuário assume total responsabilidade pelo seu uso.
