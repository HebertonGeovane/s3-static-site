#  Projeto de Site Estático com AWS S3

Este repositório contém os arquivos e instruções utilizados na **atividade prática do módulo Amazon S3**, realizada pelos alunos do curso **AWS re/Start**.

##  Descrição da Atividade

Esta atividade prática tem como objetivo reforçar o conteúdo do módulo **Amazon S3**, colocando em prática os conceitos de criação de buckets, permissões, políticas públicas e hospedagem de sites estáticos na nuvem.  
Os alunos devem criar, configurar e publicar seu próprio site em HTML/CSS usando um bucket no S3.

---

## 🚀 Objetivo

Aprender a configurar e hospedar um site estático  no **Amazon S3**, tornando-o acessível publicamente.

---

## 📘 O que você vai aprender

- O que é o Amazon S3
- Diferença entre sites estáticos e dinâmicos
- Como criar um bucket S3 e configurar a hospedagem estática
- Como lidar com erro 403 (Access Denied)
- Como aplicar uma política pública de leitura

---

## ☁️ O que é o Amazon S3?

O **Amazon S3 (Simple Storage Service)** é um serviço da AWS que permite armazenar arquivos na nuvem de forma segura, escalável e acessível. Ideal para guardar imagens, vídeos, documentos e também hospedar sites estáticos.

---

## 🧱 O que é um site estático?

Um **site estático** é composto apenas por arquivos HTML, CSS e JavaScript. Ele não depende de servidores ou bancos de dados para gerar conteúdo dinâmico, tornando-se leve, rápido e de baixo custo.

**Exemplos**:
- Portfólios pessoais
- Currículos online
- Landing pages
- Sites institucionais simples

---

## 🧰 Tecnologias Utilizadas

- **Amazon S3 (AWS)**
- **HTML5**
- **CSS3**
- **AWS Console**

---

## 📁 Conteúdo do Repositório

- `index.html` – Página principal do site
- `img/` – Pasta com imagens utilizadas no projeto

📥 [Clique aqui para baixar os arquivos do site (index.html + img)](https://drive.google.com/drive/folders/1xz2orA4gDGiVlGnnnylb2rjUYOG6Rbi2?usp=sharing)

---

## 🧪 Etapas da Atividade

### 1️⃣. Criar um Bucket no Amazon S3

- Acesse o [Console da AWS](https://aws.amazon.com/console/)
- Vá para **S3 > Criar bucket**
- Escolha um nome único, ex: `meu-site-nuvem-pratica`
- Desmarque a opção **"Bloquear acesso público"**
- Finalize com configurações padrão

📸 *Tirar print da criação do bucket*

<img width="1888" height="869" alt="image" src="https://github.com/user-attachments/assets/97d0841a-1ab0-488f-8499-f7316459b451" />

<img width="1897" height="827" alt="image" src="https://github.com/user-attachments/assets/8b2fb039-4dda-4f71-b27f-e27881072724" />

---

### 2️⃣. Fazer Upload dos Arquivos

- Faça upload de:
  - `index.html`
  - Pasta `img/` com imagens

📸 *Tirar print do upload realizado com sucesso*

<img width="1806" height="753" alt="image" src="https://github.com/user-attachments/assets/6c56a329-363d-4b10-989b-e4196b6aaace" />


---

### 3️⃣. Ativar Hospedagem Estática

- Vá até **Propriedades** do bucket
- Ative **Hospedagem de site estático**
- Configure:
  - Documento de índice: `index.html`
  - Documento de erro: `error.html` (opcional)
- Copie o **Endpoint**

📸 *Tirar print com a URL da hospedagem ativada*

<img width="1547" height="803" alt="image" src="https://github.com/user-attachments/assets/f2c871a4-279d-4f4b-9e1a-4379156c63ed" />

---
### Tentar acessar o site
Você verá um erro:  

<img width="1554" height="552" alt="image" src="https://github.com/user-attachments/assets/4931de3e-61c1-4517-8d5e-843c524eef21" />

❗
 POR QUE ISSO ACONTECE? 
Sem uma política de permissão pública no bucket, ninguém pode acessar os 
arquivos, nem mesmo o site estático.


### 4️⃣. Corrigir Erro 403 com Política Pública

Caso o site retorne erro de acesso (403 Access Denied):

- Vá até **Permissions > Bucket Policy**
- Insira a seguinte política (troque o nome do bucket):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-cloud-site-practice/*"
    }
  ]
}

```
<img width="1530" height="547" alt="image" src="https://github.com/user-attachments/assets/8a901026-d0ad-4ccb-877f-e7fb18bdac55" />

Substitua my-cloud-site pelo nome real do seu bucket.

- Salve a política

### 5️⃣. Acessar o Site Publicado 🎉
Volte para Propriedades > Hospedagem de site estático

Acesse o link do Endpoint

📸 Tirar print da página no navegador funcionando corretamente

<img width="1909" height="956" alt="image" src="https://github.com/user-attachments/assets/a9f0f288-9bac-42a8-bc74-4763a8e1d1ac" />

<img width="1904" height="946" alt="image" src="https://github.com/user-attachments/assets/aa2ab6bf-e1c3-40b9-839b-df408a33b175" />

<img width="1919" height="945" alt="image" src="https://github.com/user-attachments/assets/89ffb854-3a40-40c2-8bf2-9d2cd7ec0215" />

<img width="1913" height="955" alt="image" src="https://github.com/user-attachments/assets/df87b751-61fd-4b7d-bf40-efbd84b03145" />

<img width="1919" height="942" alt="image" src="https://github.com/user-attachments/assets/09572786-b708-4eaa-8a6f-5d2e870f7803" />

<img width="1914" height="948" alt="image" src="https://github.com/user-attachments/assets/c7db16b5-5f66-496e-a274-1b2d3856ba1d" />

### 👍 Parabéns!
Você concluiu com sucesso Atividade Publicação de Site Estático com AWS S3 

###  Por que isso é importante?

> Compreender como hospedar arquivos na nuvem de forma simples e rápida  
> 
> Aprender sobre controle de acesso e permissões em buckets S3  
> 
> Desenvolver habilidades práticas em cloud computing com foco em **armazenamento e entrega de conteúdo**  
> 
> Avançar na trilha rumo à **certificação AWS Cloud Practitioner**  

---

## 🛠 Tecnologias Utilizadas

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" alt="AWS" width="80" height="60"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML" width="60" height="60"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" alt="Bash" width="60" height="60"/>
</p>

---

### 👨‍🏫 Criado por [Heberton Geovane](https://www.linkedin.com/in/heberton-geovane/)

