# 🦷 DentiBoom

> Site de apresentação do DentiBoom, aplicativo Android que ajuda crianças a criar o hábito da escovação e apoia os pais no acompanhamento da rotina.

---

## 📋 Descrição

O **DentiBoom** é um projeto de extensão desenvolvido por estudantes de Engenharia da Computação. O aplicativo transforma a escovação em uma atividade divertida, com gamificação, música e um timer que guia a criança pelas regiões da boca. Os pais e responsáveis acompanham a rotina pelo histórico salvo no próprio aparelho.

Este repositório contém o **site público do projeto**: uma página única que apresenta o problema, a proposta do app, as funcionalidades, a equipe e a área de download.

### Funcionalidades do aplicativo

- Gamificação da escovação
- Timer por regiões da boca
- Música e feedback visual
- Conteúdos educativos (vídeos em produção, publicados somente após validação clínica)
- Status e histórico salvos no aparelho
- Perfil da criança e configurações, sem login

### Seções do site

| Seção | Conteúdo |
|---|---|
| Início | Mascote, proposta do app e botão de download |
| Projeto | Por que o projeto existe e para quem ele é feito |
| Funcionalidades | Recursos do app e demonstração interativa da escovação por quadrantes |
| Download | Área do APK para Android e passo a passo de instalação |
| Equipe | Integrantes e suas funções |

---

## 🏗️ Arquitetura

O site é estático: um único arquivo HTML com CSS e JavaScript embutidos. A imagem do mascote também está embutida no arquivo, em base64. Os únicos recursos externos são as fontes e a biblioteca de animação.

```
                ┌──────────────────────────┐
                │        index.html        │
                │  HTML + CSS + JavaScript │
                │  mascote embutido (WebP) │
                └────────────┬─────────────┘
                             │ carrega
            ┌────────────────┴────────────────┐
            ▼                                 ▼
   ┌──────────────────┐             ┌──────────────────┐
   │   Google Fonts   │             │   GSAP 3.12.5    │
   │ Baloo 2 · Nunito │             │ (cdnjs, opcional)│
   └──────────────────┘             └──────────────────┘
                             │
                             ▼
            ┌──────────────────────────────────┐
            │ Navegador (desktop e celular)    │
            │ tema claro/escuro automático     │
            └──────────────────────────────────┘
```

Sem conexão com a internet, o site continua funcionando: as fontes são trocadas por fontes do sistema e as animações de entrada são desativadas.

### Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 | Estrutura semântica e acessível |
| CSS3 | Layout responsivo, tema claro e escuro via `prefers-color-scheme` |
| JavaScript | Demonstração do timer por quadrantes |
| [GSAP 3.12.5](https://gsap.com/) | Animações de entrada e do mascote |
| [Google Fonts](https://fonts.google.com/) | Baloo 2 (títulos) e Nunito (texto) |

### Acessibilidade

- Link "Pular para o conteúdo" e foco visível no teclado
- Animações desligadas quando o sistema pede `prefers-reduced-motion`
- Contraste de cores adequado nos dois temas
- Layout ajustado para telas a partir de 360 px, sem rolagem horizontal

---

## 📁 Estrutura do Projeto

```
dentiboom/
├── index.html    # Site completo (HTML, CSS, JS e imagem do mascote)
└── README.md     # Esta documentação
```

---

## 📲 Download do Aplicativo

O botão de download aparece como **"Disponível em breve"**. Quando a versão final do APK for publicada, o botão no `index.html` passa a apontar para o link de download do arquivo.

---

## 👥 Equipe

| Integrante | Função |
|---|---|
| Amanda | Validação clínica dos conteúdos |
| Davi | Infraestrutura e publicação do app |
| Eloise | Telas do app e geração de conteúdo |
| Gabriel | Banco de dados local, vídeos e revisão técnica |
| Gabriela (Gabi) | Site, experiência visual e página de download |
| Mariana | Coordenação de QA e release |

---

*Projeto de extensão · Engenharia da Computação · 2026. Documentação gerada em 24/10/2026.*
