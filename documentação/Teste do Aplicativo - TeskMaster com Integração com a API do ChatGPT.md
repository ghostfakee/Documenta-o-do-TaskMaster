
# Objetivo do Teste

Testar a funcionalidade de um bloco de notas simples que integra a API do ChatGPT para fornecer respostas automáticas baseadas no texto selecionado pelo usuário.

# Fluxo do Teste

#### 1. Preparação

- O aplicativo deve ser aberto e garantir que a API do ChatGPT esteja corretamente configurada.
    
- O usuário deve ser capaz de selecionar qualquer trecho de texto no bloco de notas.
    

#### 2. Passos do Teste

- Passo 1: Abrir o aplicativo.
    
- Passo 2: Inserir um texto qualquer na área de edição (bloco de notas).
    
- Passo 3: Selecionar uma parte do texto para ser enviado à IA.
    
- Passo 4: Clicar no botão "Enviar" para enviar o texto selecionado para a API do ChatGPT.
    
- Passo 5: O texto selecionado será enviado para a API, e o ChatGPT deve fornecer uma resposta que será exibida em uma área separada no aplicativo.
# Testes Específicos

#### Testar a Seleção de Texto

- Objetivo: Garantir que o usuário possa selecionar qualquer trecho de texto para ser enviado à IA.
    
- Passos:
    

- Digitar um parágrafo no bloco de notas.
    
- Selecionar parte do texto com o mouse.
    
- Garantir que o texto selecionado seja copiado corretamente para a variável que será enviada para a API.
    

- Resultado Esperado:
    

- O texto selecionado deve ser corretamente passado para a requisição da API.
    

#### 2. Testar o Envio do Texto para a API do ChatGPT

- Objetivo: Verificar se o texto selecionado é corretamente enviado para a API do ChatGPT.
    
- Passos:
    

- Selecionar o texto como no teste anterior.
    
- Clicar no botão "Enviar".
    

- Resultado Esperado:
    

- O texto selecionado deve ser enviado corretamente para a API.
    
- O código de resposta HTTP da API deve ser 200 (OK) se a requisição for bem-sucedida.
    

#### 3. Testar a Exibição da Resposta da IA

- Objetivo: Verificar se a resposta da API do ChatGPT é exibida corretamente na interface do usuário.
    
- Passos:
    

- Enviar um texto à API.
    
- Aguardar a resposta da IA.
    
- Verificar se a resposta aparece corretamente na área de texto dedicada para a resposta.
    

- Resultado Esperado:
    

- O campo de resposta deve ser preenchido com a resposta fornecida pela IA.
    

#### 4. Testar o Tratamento do Erro 429 (Too Many Requests)

- Objetivo: Garantir que o aplicativo lide corretamente com o erro 429, que ocorre quando muitas requisições são feitas em um curto período.
    
- Passos:
    

- Enviar várias requisições em sequência rápida.
    
- Verificar se o código aguarda o tempo adequado entre as requisições quando o erro 429 ocorre.
    

- Resultado Esperado:
    

- O aplicativo deve aguardar o tempo necessário (indicado no cabeçalho Retry-After ou um valor default de 10 segundos).
    
- Após o tempo de espera, a requisição deve ser tentada novamente.
    

#### 5. Testar o Bloqueio de Múltiplos Cliques no Botão

- Objetivo: Garantir que o botão de envio seja desabilitado durante o processo de envio para evitar múltiplos cliques.
    
- Passos:
    

- Clicar no botão "Enviar".
    
- Clicar novamente no botão rapidamente.
    

- Resultado Esperado:
    

- O botão deve ser desabilitado logo após o primeiro clique e reabilitado após a resposta ser recebida, impedindo múltiplos envios.
    

#### 6. Testar o Funcionalidade do Delay de Espera (Se necessário)

- Objetivo: Verificar se o delay configurado entre as requisições (caso o erro 429 ocorra) funciona corretamente.
    
- Passos:
    

- Enviar múltiplas requisições rápidas.
    
- Verificar se o aplicativo aguarda a quantidade de tempo especificada antes de fazer uma nova tentativa.
    

- Resultado Esperado:
    

- O aplicativo deve aguardar o tempo de espera configurado e, após o delay, deve realizar uma nova tentativa de enviar o texto para a API.
    

# Considerações de Teste


#### 1. Testes de Estabilidade
    

- Testar o envio de vários textos e garantir que o aplicativo não trave ou gere falhas inesperadas.
    

#### 2. Testes de Conectividade
    

- Verificar se o aplicativo lida adequadamente com falhas de rede, como perda de conexão com a internet.
    
- Garantir que o erro seja tratado e exibido ao usuário com uma mensagem adequada.
    

#### 3. Testes de Usabilidade
    

- O botão "Enviar" deve ser fácil de encontrar e clicar.
    
- A interface deve ser clara e mostrar claramente onde o usuário deve inserir o texto e onde a resposta da IA será exibida.
    

---

#### Resultado Esperado Final

Após realizar os testes acima, o aplicativo deve:

- Enviar corretamente o texto selecionado para a API do ChatGPT.
    
- Exibir a resposta da IA na interface do usuário.
    
- Lidar adequadamente com erros, como o erro 429, aguardando o tempo necessário para tentar novamente.
    
- Impedir múltiplos cliques no botão de envio.
    
- Ser estável e fácil de usar, sem falhas ou travamentos.
    
