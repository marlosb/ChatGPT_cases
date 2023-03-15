## Casos de uso do ChatGPT

A intenção desse projeto é mostrar alguns casos de usos do ChatGPT para o dia a dia das empresas e instituições.

### Requisitos
 - Python 3.11 (ele foi desenvolvido e testado no Python 3.11.1)
 - Azure CLI [link (https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli)]
 - bibliotecas do requirements.txt

 Antes de abrir os notebooks certifique-se de estar logado no azure pela Azure CLI.
 ' az login'

 Todos os notebooks usam a autenticação via Azure CLI, portanto, se não estiver logado no Azure CLI os notebooks vão falhar.

 ### Uso

  - 1 provision resources.ipynb
  Esse notebook cria os recursos, o Resource Group, Cognitive Services Account para OpenAI e faz o deployment do modelo gpt35-turbo (que é o modelo do ChatGPT)

  - 2 Coho Alimentos.ipynb
  - 3 Contoso Cosméticos.ipynb
  - 4 Dados sintéticos.ipynb
  Esses notebooks se conectam aos recursos criados. Instanciam um prompt, token encoder e objeto para comunicar com a API. Envia os exemplos do casos.

  - 9 delete resources.ipynb
  Esse notebook deleta os recursos criados.
