<p align="center">
<img alt="Isaac Oolibama — Analista de Sistemas" src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,50:334155,100:38BDF8&height=180&section=header&text=Isaac%20Oolibama&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=34&desc=Analista%20de%20Sistemas%20%C2%B7%20ERP%20Sankhya%20%C2%B7%20Oracle%20%C2%B7%20Automa%C3%A7%C3%A3o&descAlignY=54&descSize=16" />
</p>p>

<p align="center">
<a href="https://isaacoolibama.github.io"><img alt="Portfólio" src="https://img.shields.io/badge/Portfólio-0f172a?style=flat-square&logo=vercel&logoColor=38BDF8" /></a>a>
<a href="https://linkedin.com/in/isaacoolibama"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" /></a>a>
<a href="mailto:isaacors@gmail.com"><img alt="E-mail" src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" /></a>a>
<img alt="Localização: Açailândia, MA" src="https://img.shields.io/badge/Açailândia,_MA-1E293B?style=flat-square&logo=googlemaps&logoColor=38BDF8" />
</p>p>

**Gestor de TI** por formação, com base em **Administração de Empresas**, possuo Pós-Graduação em Ciência de Dados & AI, Engenharia de Dados, e MBA em Gestão Estratégica de TI, atuo como **Analista de Sistemas** a frente do setor de tecnologia, na melhoria continua de processos internos e externos da organização com parceiros, amigos e clientes.

Também sou **professor-conteudista** no Bacharelado em Sistemas de Informação (EaD), onde escrevo material didático e produzo video-aulas contribuindo com o desenvolvimento de alunos do ensino superior.

---

## 🏭 Projetos aplicáveis em produção

Alguns resultados:

| Entrega | Resultado |
|---|---|
| Otimização de procedure de produção (Oracle) | De **8+ min com timeout** para **34 s** via indexação |
| Automação de reajuste salarial coletivo | **~1500 colaboradores** processados via API Sankhya (Python) |
| Tuning de JVM (WildFly / OCI) | Heap de 24 GB → 12 GB, eliminação de pressão de swap |
| Expansão de campos fiscais (LC 214/2025) | **~70 tabelas** alteradas em produção com rollback validado |
| Triggers, procedures, functions | Detecção, investigação e melhorias das regras de negócio através de PL/SQL |

---

## 🚀 Estudos de caso

> A maior parte do que desenvolvo é software interno entrega direta em produção.
> > Estes quatro repositórios abrem a **arquitetura e as decisões técnicas** de sistemas que estão
> > > rodando em produção hoje — sem o código proprietário.
> > >
> > > <table>
  <tr>
    <td width="50%" valign="top">

      ### 📄 [NFS-e Sync — Sankhya ERP](https://github.com/isaacoolibama/sankhya-nfse-sync-case-study)

      Módulo Java implantado dentro do ERP que sincroniza NFS-e do **Portal Nacional** via mTLS
      com certificado ICP-Brasil, detecta cancelamentos por duas origens independentes e gera o DANFSe.

      `Java 8` `Maven shade` `Oracle` `WildFly` `Quartz` `mTLS` `openhtmltopdf`

      **Destaques:** fat JAR com *relocation* para conviver com o classloader do WildFly · sincronização
      em 3 fases com paralelismo escalonado · `LOCK TABLE` + `INSERT WHERE NOT EXISTS` contra corrida ·
      cadeia de fallback do DANFSe.

      </td>
      <td width="50%" valign="top">

      ### 💰 [Reajuste Salarial em Massa](https://github.com/isaacoolibama/reajuste-salarial-case-study)

      App desktop que aplica o reajuste coletivo de **todos os colaboradores** no Sankhya Om,
      com conferência antes de gravar e auditoria depois.

      `Tauri` `Rust` `Python 3.12` `Sankhya Om`

      **Destaques:** quem calcula é o servidor — zero aritmética local no caminho crítico, zero
      divergência de arredondamento · das 5 etapas, só uma escreve · lançamentos avulsos geram
      `.sql` para revisão humana em vez de `INSERT` direto.

      </td>
      </tr>
      <tr>
      <td width="50%" valign="top">

      ### ⏱️ [Ponto Eletrônico — Confronto Operacional](https://github.com/isaacoolibama/pontotel-checkin-case-study)

      App desktop que consolida duas fontes de verdade sobre a mesma pessoa — sistema de ponto e
      ERP — e entrega o confronto por data em tela e em Excel.

      `Java 17` `Spring Boot 3.5` `React 18` `TypeScript` `Electron 31` `SQLite`

      **Destaques:** backend Spring Boot dentro do app desktop, servindo em loopback · cache SQLite
      para operação parcial e recálculo rápido · sessão do próprio usuário, revalidada por ação.

      </td>
      <td width="50%" valign="top">

      ### 📡 [Monitoramento e Alertas Multicanal](https://github.com/isaacoolibama/monitoramento-alertas-case-study)

      Stack de monitoramento em Docker que distribui alertas por dois canais independentes e
      renova certificados automaticamente.

      `Node.js 22` `Docker Compose` `Uptime Kuma` `whatsapp-web.js` `Discord Gateway` `Nginx`

      **Destaques:** WhatsApp sem serviço externo (Puppeteer no container) · o bot reporta o próprio
      estado no canal que não caiu · alerta por transição de estado, não por checagem · `certificate has
      expired` detectado e renovado via SSH.

      </td>
      </tr>
      </table>

      ---

      ## 🔒 Outros projetos privados

      <details open>
      <summary><b>Ecossistema Sankhya · NFS-e · fiscal</b></summary>

      <br/>

      | Projeto | Descrição | Stack |
      |---|---|---|
      | **sankhya-xml-compras** | Lançamento de nota de compra a partir do Portal de XML, com padrões por parceiro. Tela própria sobre *view* Oracle espelhada, para contornar a limitação de botões de ação na tela nativa | `Java` `Oracle` `Sankhya` |
      | **emissao-nfse-portalnacional** | Biblioteca Python de emissão de NFS-e no Portal Nacional — DPS, assinatura XMLDSig, validação contra XSD oficiais, cancelamento, substituição, eventos e distribuição DF-e. Leiaute v1.01 | `Python 3.10+` `lxml` `cryptography` `httpx` |
      | **processador-nfse-portal-nacional-java** | CLI Spring Boot que consulta NFS-e por certificado digital, extrai XML via API SEFIN e gera DANFSe em PDF com mapa de rastreabilidade do lote | `Java 17` `Spring Boot` `mTLS` |
      | **Integração Ponto Eletrônico ↔ ERP** | Integração Java para o ERP: consulta a API de ponto, processa movimentos por período, atualiza equipes e registra execução em tabelas de log | `Java 8` `JAPE/ModelCore` |
      | **Cobrança de Notas Fiscais Pendentes** | Identifica e notifica sobre notas fiscais pendentes de ação no ERP | `Java` |

      </details>

      <details>
      <summary><b>Aplicações desktop corporativas</b></summary>

      <br/>

      | Projeto | Descrição | Stack |
      |---|---|---|
      | **Gestão de Documentos Trabalhistas** | Plataforma híbrida (desktop + web) de gestão, versionamento e auditoria de documentos trabalhistas. Monorepo com API, worker de jobs e app | `Fastify` `TypeScript` `PostgreSQL 16` `Redis` `BullMQ` `Electron` `Docker` `PNPM Workspace` |
      | **gcp-gestao-compras-pagamentos** | Gestão do fluxo de compras e pagamentos por data e centro de resultado, com autenticação via ERP, anexos em armazenamento Samba e API própria como fonte oficial de dados | `Electron 35` `Next.js 15` `React 18` `TypeScript` `PostgreSQL` |
      | **Automação Financeira — PIX / Viagens** | Automação de lançamento de tarifas PIX e despesas de viagem no ERP, com auto-update embutido | `Next.js 14` `Electron 27` `TypeScript` |
      | **planejamento-estrategico-gerador-sql** | Processa planilhas de planejamento estratégico e gera o SQL de inserção validado; núcleo Python com interface desktop | `Tauri` `React` `Python` |
      | **Processador de Holerites — OCR** | Processamento em lote de holerites: OCR extrai os dados, divide o PDF por funcionário e renomeia com base no cadastro do ERP | `Python` `OCR` `tkinter` `PyInstaller` |
      | **cadastro-processos-detran** | Painel de cadastro e acompanhamento de processos veiculares, com importação de dados de CRLV-e por OCR | `Next.js 16` `React 19` `Electron` `tesseract.js` `pdfjs-dist` |

      </details>

      <details>
      <summary><b>Infraestrutura e plataformas</b></summary>

      <br/>

      | Projeto | Descrição | Stack |
      |---|---|---|
      | **Helpdesk via WhatsApp** | Helpdesk em que o colaborador abre chamado pelo WhatsApp e o analista atende por interface web, em tempo real, com protocolo rastreável e upload de mídia | `React` `Node.js` `PostgreSQL` `WebSockets` `JWT` `Docker` |
      | **Monitoramento e Alertas (ERP)** | Stack de monitoramento e alertas multicanal — [estudo de caso acima](https://github.com/isaacoolibama/monitoramento-alertas-case-study) | `Node.js 22` `Docker` `Uptime Kuma` |
      | **conferencia-resistencia** | Plataforma devocional com liberação de conteúdo validada no servidor por fuso horário — o conteúdo futuro nunca chega ao navegador | `Next.js 16` `React 19` `TypeScript` `Tailwind 4` |

      </details>

      ---

      ## 🌍 Projetos públicos

      | Projeto | Descrição |
      |---|---|
      | [**WinLean**](https://github.com/isaacoolibama/WinLean) | Debloat, privacidade e performance para Windows 10/11. TUI em Rust (ratatui), rollback por *journal* JSON, PT/EN |
      | [**anydesk-reset**](https://github.com/isaacoolibama/anydesk-reset) | Ferramenta gratuita para resetar a identidade (ID) do AnyDesk no Windows |
      | [**system-info-tool**](https://github.com/isaacoolibama/system-info-tool) | Coleta de informações de sistema Windows em PowerShell |
      | [**isaacoolibama.github.io**](https://github.com/isaacoolibama/isaacoolibama.github.io) | Portfólio e currículo |

      ### 🎓 Projetos de formação (Oracle ONE · Alura)

      | Projeto | Descrição |
      |---|---|
      | [**literalura**](https://github.com/isaacoolibama/literalura) | Catálogo de livros via API Gutendex, com persistência em PostgreSQL — Java, Spring Boot |
      | [**forumhub**](https://github.com/isaacoolibama/forumhub) | API REST de fórum com autenticação JWT e Spring Security — Java, Spring Boot |
      | [**conversor-de-moedas**](https://github.com/isaacoolibama/conversor-de-moedas) | Conversor de moedas via linha de comando, com histórico das últimas conversões — Java |
      | [**gcp-quiz**](https://github.com/isaacoolibama/gcp-quiz) | Plataforma de quiz com painel administrativo em tempo real, usada em atividade de extensão — React, Firebase |
      | [**jogo-numero-secreto**](https://github.com/isaacoolibama/jogo-numero-secreto) | Jogo de adivinhação de número secreto — HTML, CSS, JavaScript |
      | [**amigo-secreto**](https://github.com/isaacoolibama/amigo-secreto) | Sorteio de amigo secreto — HTML, CSS |

      ---

      ## 🛠️ Stack

      <div align="center">

      <a href="https://skillicons.dev">
      <img alt="Java, Python, TypeScript, JavaScript, Rust, Spring, Node.js, React, Next.js, Electron, Tauri, PostgreSQL, Docker, Linux, Git, PowerShell" src="https://skillicons.dev/icons?i=java,python,ts,js,rust,spring,nodejs,react,nextjs,electron,tauri,postgres,docker,linux,git,powershell&theme=dark&perline=8" />
      </a>

      <br/><br/>

      ![Oracle 19c](https://img.shields.io/badge/Oracle_19c-1E293B?style=flat-square&logo=oracle&logoColor=F80000)
      ![PL/SQL](https://img.shields.io/badge/PL%2FSQL-334155?style=flat-square)
      ![Sankhya ERP](https://img.shields.io/badge/Sankhya_ERP-475569?style=flat-square)
      ![WildFly](https://img.shields.io/badge/WildFly-1E293B?style=flat-square)
      ![Maven](https://img.shields.io/badge/Maven-334155?style=flat-square&logo=apachemaven&logoColor=white)
      ![Redis](https://img.shields.io/badge/Redis-1E293B?style=flat-square&logo=redis&logoColor=DC382D)
      ![SQLite](https://img.shields.io/badge/SQLite-334155?style=flat-square&logo=sqlite&logoColor=white)
      ![Nginx](https://img.shields.io/badge/Nginx-1E293B?style=flat-square&logo=nginx&logoColor=009639)
      ![OCI](https://img.shields.io/badge/Oracle_Cloud-1E293B?style=flat-square&logo=oracle&logoColor=F80000)
      ![Tailwind](https://img.shields.io/badge/Tailwind-334155?style=flat-square&logo=tailwindcss&logoColor=38BDF8)
      ![mTLS](https://img.shields.io/badge/mTLS_·_ICP--Brasil-1E293B?style=flat-square)
      ![Agentic AI](https://img.shields.io/badge/Agentic_AI-2563EB?style=flat-square)

      </div>

      ### Distribuição real de código

      > O cartão de linguagens do GitHub só enxerga repositórios públicos. Ao todo, considerando
      > públicos e privados, são **38 repositórios**.

      ---

      ## 🎓 Formação

      - **Gestor de TI**
      - **Bacharelado em Administração**
      - **MBA em Gestão Estratégica de TI**
      - **Pós-Graduação em Ciência de Dados & Inteligência Artificial**
      - **Pós-Graduação em Engenharia de Dados**

      ## 🏆 Certificações & Cursos de Especialização

      **🤖 Inteligência Artificial & Agentes Autônomos**

      - Nano Course em Agentes Autônomos (Agentic AI) — FIAP (2026)
      - Engenharia de Prompt e aplicação de LLMs em automação corporativa

      **☁️ Cloud & Banco de Dados**

      - Certificação OCI Foundations Associate — Oracle (2025)
      - Administração, tuning e consultas avançadas em Oracle Database e PostgreSQL
      - Oracle Next Education (ONE) — Oracle/Alura

      **💼 Gestão, Processos & ERP**

      - Especialização prática no ecossistema Sankhya ERP (customização, dicionário de dados, regras de negócio e bot de automação)
      - Mapeamento de processos de negócio, indicadores de desempenho (KPIs) e análise contábil/financeira
      - Melhoria de rotinas em todos os setores organizacionais, do operacional a diretoria

      ---

      <p align="center">
      <img alt="GitHub Streak" height="165" src="https://streak-stats.demolab.com/?user=isaacoolibama&theme=tokyonight&hide_border=true&background=0F172A&stroke=38BDF8&ring=38BDF8&fire=38BDF8" />
      </p>

      <p align="center">
      <sub>💡 Currículo completo em <a href="https://isaacoolibama.github.io"><b>isaacoolibama.github.io</b></a> · Código-fonte dos projetos privados disponível mediante conversa</sub>
      </p>
      
  </tr>
</table>
