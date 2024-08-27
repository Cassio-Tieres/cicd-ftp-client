## Pipeline CI/CD para FTP-CLIENT

Projeto de estudo de DevOps para configurar um pipeline de CI/CD para um cliente FTP.

## Tools
* GitHub Actions
* YML
* Secrets Keys

## Explicação dos Status de deploy
Utilizando condicionais para verificar se o envio obteve sucesso ou falhou. O código também possui a capacidade de gerar Logs ao enviar os pushes para a branch main ou master.

```yml
- name: Definir status de sucesso
if: ${{ success() }}
run: echo "OK! Código enviado para produção" | tee status_message.log

- name: Definir status de error
if: ${{ failure() }}
run: echo "NOK! Error ao tentar enviar para produção" | tee status_message.log
```

## Configuração de secrets
Para manter a segurança do acesso ao meu cliente FTP, criei secrets aqui no meu repositório com as credenciais de acesso. Dessa maneira, mantenho meu código servidor livre de invasões, pois não manteremos estas credenciais expostas.

Para configurar as secrets da sua action, basta acessar:

````
Settings --> Secrets and variables --> Actions --> New repository keys
````

## Como utilizar
Clone este repositório para a raíz do seu projeto e crie as secrets keys necessárias para o acesso ao servidor FTP.

Você não precisa fazer nenhum commit para este repositório com as suas configurações, basta utilizar livremente.



Desenvolvido por: Cássio V. T. Bomfim.

### obs
O arquivo .yml está sendo enviado via push utilizando um "_yml" ao invés de ".yml" para evitar problemas ao dar push, pois este repositório trata-se apenas de um estudo de caso.