# 📍 Check-in de Localização — Web App

Aplicação web *single-file* (HTML, CSS e JavaScript puro) projetada para captura rápida de coordenadas geográficas em campo e envio automatizado diretamente para uma base no **Google Sheets** via **Google Forms**, hospedada gratuitamente no **GitHub Pages**.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222222?style=for-the-badge&logo=githubpages&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)

---

## 🎯 Problema & Solução

Coletar pontos de localização em campo usando formulários tradicionais costuma gerar erros de digitação, lentidão no celular e atrito para o usuário. 

Este projeto resolve esse gargalo com uma interface leve e responsiva que **captura o GPS automaticamente** com um clique, valida as coordenadas no navegador e alimenta uma planilha estruturada em tempo real — sem necessidade de servidor backend, banco de dados pago ou processos de build.

### Fluxo de Dados

```text
┌─────────────────────────┐      POST (hidden_iframe)      ┌─────────────────────────┐
│   Interface Web (PWA)   │ ─────────────────────────────► │      Google Forms       │
│  Geolocation API / Form │   application/x-www-form-url   │     (/formResponse)     │
└─────────────────────────┘                                └────────────┬────────────┘
                                                                        │
                                                           Registro automático
                                                                        ▼
                                                           ┌─────────────────────────┐
                                                           │      Google Sheets      │
                                                           │  (Timestamp + Dados)    │
                                                           └─────────────────────────┘
