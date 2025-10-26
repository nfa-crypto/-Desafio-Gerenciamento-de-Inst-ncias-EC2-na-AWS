# -Desafio-Gerenciamento-de-Inst-ncias-EC2-na-AWS
Este repositório faz parte do **laboratório da DIO** sobre **gerenciamento de instâncias EC2 na AWS.
## 🎯 Objetivos de Aprendizagem

Ao final deste desafio, pude:
- Aplicar os conceitos aprendidos em um ambiente prático da AWS;
- Documentar os processos técnicos de forma organizada;
- Utilizar o **GitHub** como ferramenta para compartilhamento de documentação técnica.

---
## Explicando os 4 serviços da AWS: S3, Lambda, EC2 e EBS

## 💾 Amazon S3 (Simple Storage Service)

- É o armazenamento de objetos da AWS, você pode pensar nele como um pendrive infinito na nuvem.
- Armazena arquivos como imagens, vídeos, PDFs, planilhas etc.
- Os arquivos ficam em “buckets” (pastas virtuais).
- Muito usado para backup, sites estáticos, armazenar logs e dados de análise.
## Exemplo:
- Salvar as fotos dos usuários de um site dentro de um bucket S3, acessando por link público ou API.

## 🖥️ Amazon EC2 (Elastic Compute Cloud)

- É o serviço de servidores virtuais da AWS. Pense nele como um computador remoto, onde você instala o que quiser.
- Você escolhe o tipo de instância (CPU, memória, sistema operacional).
- Pode conectar via SSH e instalar programas (como Apache, MySQL, Node.js).
- É ideal para aplicações que ficam ativas 24h.
## Exemplo:
- Hospedar o backend de um site, um banco de dados, ou um sistema de gestão.

## 💽 Amazon EBS (Elastic Block Store)

- É o disco rígido (HD/SSD) que fica conectado à sua instância EC2.
- Armazena dados persistentes da máquina virtual (EC2).
- Se a instância for reiniciada, os dados continuam lá.
- Pode ser redimensionado ou conectado a outras instâncias.
## Exemplo:
- Guardar o sistema operacional e os arquivos da sua EC2 — como o C:\ ou /root de um computador.

## ⚡ AWS Lambda

- É o serviço de computação sem servidor (serverless). Você não precisa criar uma instância EC2 — apenas envia seu código e a AWS executa quando for necessário.
- Você paga somente pelo tempo de execução (milissegundos).
- Ideal para tarefas automáticas e rápidas.
## Exemplo:
- Sempre que uma imagem é enviada para o S3, uma função Lambda é disparada para redimensionar a imagem automaticamente.

--
## Resumo do padrão EC2 + EBS
- Usuário acessa app/site → EC2 processa → EBS armazena dados persistentes
- EC2: “computador virtual” que processa dados, roda aplicações e servidores.
- EBS: “HD virtual” que mantém os dados mesmo se o EC2 for desligado ou reiniciado.
- Vantagem: armazenamento confiável e escalável, necessário para aplicações que precisam de persistência de dados.
<img width="1342" height="737" alt="Diagrama EC2_EBS" src="https://github.com/user-attachments/assets/78d3694b-d332-432c-b4dc-9aef65b0a419" />

--
## Resumo do padrão S3 + Lambda Fucntion
- Usuário envia arquivo para o S3:
- Um bucket S3 é criado (ex: imagens-brutas).
- Toda vez que alguém faz upload, um evento é disparado.

- Evento dispara a função Lambda:
- Lambda está “ouvindo” esse bucket.
- Quando detecta o novo arquivo, Lambda é executada automaticamente.

- Lambda processa o arquivo:
- Pode redimensionar imagem, converter formato, mover arquivo, enviar notificação etc.

- Resultado é salvo:
- Lambda salva a saída em outro bucket (ex: imagens-processadas) ou faz qualquer ação programada.
<img width="1342" height="737" alt="Diagrama S3_Lambda" src="https://github.com/user-attachments/assets/32bca5a6-cece-4557-aa38-1286716f1b8f" />

## 🧠 O que eu aprendi
- Diferença entre tipos de instâncias;
- Como gerenciar os recursos visando utilizar de forma que não haja gastos desnecessarios;
- Como criar uma instância EC2;
- Como iniciar, parar e terminar instâncias;
- Como configurar **Security Groups** para controle de acesso;
- Importância das **chaves de acesso (Key Pairs)** para autenticação segura;
- Noções básicas sobre volumes EBS.
- Funcionalidade dos serviços S3 + Lambda Function
- Funcionalidade dos serviços EC2 + EBS

🧾 Conclusão

Este desafio foi essencial para reforçar conceitos práticos sobre infraestrutura em nuvem e gerenciamento de servidores virtuais.
Documentar o processo me ajudou a entender melhor o funcionamento da AWS e a importância de boas práticas de segurança e automação.

   ---


   👩‍💻 **Natacha Ferreira de Araújo**  
💼 Projeto desenvolvido como parte do curso da [Digital Innovation One (DIO)](https://www.dio.me/)  
