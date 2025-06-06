# 01 - Primeira API

**Antes de começar, execute os passos abaixo para configurar o ambiente caso não tenha feito isso ainda na aula de HOJE: [Preparando Credenciais](../../01-create-codespaces/Inicio-de-aula.md)**

OBJETIVO: Criar a primeira api no serviço [Amazon API Gateway](https://aws.amazon.com/pt/api-gateway/) utilizando a estrutura de exemplo do painel.

1. Abra o serviço [API Gateway](https://us-east-1.console.aws.amazon.com/apigateway/main/apis?region=us-east-1) e clique em `Criar API` no canto superior direito da tela.
    
    ![](img/1.png)

2. Desça nas opções da tela até `API REST` e clique em `importar`.
   
   ![](img/2.png)

3. Clique em `API de exemplo`
   
   ![](img/3.png)

4. No canto inferior direito da tela clique em `Criar API`
5. Sua API ficará com a seguinte estrutura:
   
   ![](img/4.png)

6. Faça testes antes de executar o deploy da API. Para isso vá em `POSTS` do `/pets/`.
   
   ![](img/5.png)

7. Clique em `Teste`
8. No campo `Corpo de solicitação` cole o seguinte conteúdo:
   ``` json
   {"type": "dog", "price": 249.99}
   ```
    ![](img/6.png)
9. Na parte inferior da tela clique em `Teste`. Você executou o teste dessa chamada da sua API. Você pode ver a resposta em `Corpo de resposta` e todos os logs da chamada em `Logs`
    
    ![](img/7.png)

10. Agora sim é hora de implantar a API para ter uma URL a ser chamada. Para isso clique em `Implantar API` no canto superior direito da tela.
    
    ![](img/8.png)

11. Preencha os campos do formulário como na imagem abaixo:

    ![](img/9.png)

12. Clique em `Implantar`.
13. Pronto você criou sua primeira API no API Gateway e a URL para chamar esta no topo da tela.
14. Vamos executar chamadas de teste via POSTMAN para testar a API externamente. Clique no superior direito em `Ações do estagio` na aba `Exportar` do récem criado estagio Test. Escolha as opções:
    - Tipo de especificação de API: `Swagger`
    - Formato: `YAML`
    - Extemsões: `Exportar com extensões Postman`

    ![](img/10.png)
    
    ![](img/10-2.png)

15. Abra o Postman no seu [navegador](https://web.postman.co/). Caso não tenha cadastro, faça sua conta gratuitamente. 
16. Dentro do Postman clique em `Import`.
    
    ![](img/11.png)

17. Carregue o arquivo recem baixado do API Gateway. Após carregar o arquivo o postman ficará como na imagem abaixo:
    
    ![](img/12.png)

18. Expanda os campos até chegar em `POST Create Pet` e clique para abrir no editor. Copie o json abaixo no corpo da requisição:
    ``` json
    {
    "type": "bird",
    "price": 234.98
    }
    ```
    
    ![](img/13.png)

19. Clique em `Send` na lateral direita da tela. Você acabou de fazer uma chamada para sua API via postman.
    
    ![](img/14.png)
20. Agora você fará uma chamada de listagem. Para isso clique em `Get /pets` para abrir no editor.

    ![](img/15.png)

21. Edite o valor do campo `type` para `cat` e o valor do campo `page` para `1`.
    
    ![](img/16.png)

22. Clique em `Send` no superior direito para executar a listagem.

    ![](img/17.png)

23. Como ultimo teste, o path principal da sua API retorna um HTML quando chamada via método GET(Caso dos navegadores). Retorne ao API Gateway e copie a URL da sua API e cole no navegador.
    
    ![](img/18.png)

    ![](img/19.png)
