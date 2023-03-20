## Casos de uso do ChatGPT

A intenção desse projeto é mostrar alguns casos de usos do ChatGPT para o dia a dia das empresas e instituições (parte 1). Bem como exemplificar como adicionar contexto as conversas para controlar as informações que o ChatGPT irá usar para responder aos usuários (parte 2).

### Requisitos
 - Acesso aos modelos da OpenAI no Azure (é preciso pedir acesso via formulário no portal do Azure)
 - Python 3.11 (ele foi desenvolvido e testado no Python 3.11.1)
 - Azure CLI: [link](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli)
 - bibliotecas listadas no arquivo requirements.txt<br>
 ```pip install -r requirements.txt```

 Antes de abrir os notebooks certifique-se de estar logado no azure pela Azure CLI. Para logar, no terminal, use o comando:<br>
 ``` az login ```

 Todos os notebooks usam a autenticação via Azure CLI, portanto, se não estiver logado no Azure CLI os notebooks vão falhar.

 ### Uso

 O repositório tem 2 partes:
 Parte 1:
    O projeto consiste em 5 notebooks de jupyter, sendo:

    - 1 provision resources.ipynb<br>
    Esse notebook cria os recursos, o Resource Group, Cognitive Services Account para OpenAI e faz o deployment do modelo gpt35-turbo (que é o modelo do ChatGPT)

    - 2 Coho Alimentos.ipynb; 3 Contoso Cosméticos.ipynb; 4 Dados sintéticos.ipynb<br>
    Esses notebooks se conectam aos recursos criados. Instanciam um prompt, token encoder e objeto para comunicar com a API. Envia os exemplos do casos.

    - 9 delete resources.ipynb<br>
    Esse notebook deleta os recursos criados.

Parte 2:
    São 2 notebooks e alguns arquivos text no subdiretório data/.

    - data/<br>
    Arquivos de texto que servem como origem das informações que serão enviadas como contexto para o ChatGPT

    - 1 Deploy ada model.ipynb<br>
    Notebook que cria e faz deploymento de um modelo ada usado na identificação de similaridade

    - 3 Import and prepare data.ipynb<br>
    Notebook que faz o fluxo completo: lê os textos dos arquivos, cataloga-os para comparação e compara com cada pergunta para identificar qual o arquivo tem as informações que precisamos. Na sequencia passa essas informações como contexto para o ChatGPT junto com a pergunta do usuário.
