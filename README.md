##

# 🚀 Desafio AWS Step Functions - DIO

Este repositório contém a prática do desafio **Workflows Automatizados com AWS Step Functions**, parte da formação na [DIO](https://www.dio.me/).

O objetivo foi consolidar os aprendizados das aulas, aplicando na prática a criação de uma **State Machine** e documentando os resultados.

---


---

## 🛠️ Tecnologias e Serviços Utilizados

- **AWS Step Functions**
- **AWS Lambda (integração simples)**
- **Amazon CloudWatch (monitoramento básico)**
- **GitHub** para versionamento e documentação


---

## 📘 Código JSON

Para visualizar o código completo da máquina de estados veja o arquivo disponível em [`/state/hello-json`](./state/hello-json).

Trecho ilustrativo:

```json

    "VerificarResultado": {
      "Type": "Choice",
      "Choices": [
        {
          "Variable": "$.taskResult.resultado.status",
          "StringEquals": "ERRO",
          "Next": "TratarErro"
        },
        {
          "Variable": "$.taskResult.resultado.status",
          "StringEquals": "OK",
          "Next": "TaskFinal"
        }
      ],
      "Default": "Espera"
    },
    "TratarErro": {
      "Type": "Task",
      "Resource": "arn:aws:states:::lambda:invoke",
      "Parameters": {
        "FunctionName": "arn:aws:lambda:us-east-1:123456789012:function:tratar-erro-funcao",
        "Payload.$": "$"
      },
 

```
##
<img width="824" height="416" alt="Image" src="https://github.com/user-attachments/assets/56a1c6a1-e335-407d-b0e7-fcaf54d59184" />




##
💡 Aprendizados

A importância de definir bem os estados para prever cenários de erro.

Como o Choice State facilita a tomada de decisão dentro do fluxo.

O uso de Wait State para processos assíncronos.

Integração do CloudWatch para logs e monitoramento.

Boa prática: sempre estruturar o repositório com README, código e imagens organizados.

👉 Para mais detalhes sobre meu aprendizado, consulte o arquivo:  
[📘 meus-aprendizados](./aprendizados/meus-aprendizados)

##

📚 Recursos Úteis

- [📖 AWS Step Functions - Documentação Oficial](https://docs.aws.amazon.com/step-functions/)
- [⚡ AWS Free Tier](https://aws.amazon.com/free/)
- [📓 GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)
- [🎬 Formação DIO ](https://www.dio.me/users/patriciasavarezioliveira)

##
✍️ Autora: Ana Beatriz 
📌 Este repositório foi criado como parte do desafio da DIO.  
   Santander Code Girls - 2025

##

<a href="https://www.linkedin.com/in/ana-beatriz-m-p-ramos-936b13137/"><img src="https://img.shields.io/badge/-LinkedIn-67cb57?style=for-the-badge&logo=linkedin&logoColor=fff"></a>


