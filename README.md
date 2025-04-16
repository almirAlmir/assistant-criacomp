# Assistente Virtual para a Coordenação de Extensão do CIn/UFPE

Este projeto implementa um assistente virtual capaz de responder perguntas sobre a Coordenação de Extensão do Centro de Informática (CIn/UFPE). Ele utiliza a API da OpenAI para processar linguagem natural e a biblioteca Gradio para fornecer uma interface de chat interativa. As respostas são baseadas nos documentos fornecidos e armazenados em um vector store.

## Pré-requisitos

* **Conta OpenAI e Chave de API:** Você precisará de uma conta ativa na OpenAI e de uma chave de API válida. Certifique-se de ter a chave de API disponível.
* **Google Colab (Recomendado):** Este projeto foi desenvolvido e testado no Google Colab.
* **Arquivos PDF:** Tenha os arquivos PDF contendo as informações relevantes da Coordenação de Extensão do CIn/UFPE prontos para serem carregados. Voce pode usar os documentos contidos na pasta assistantpasta/pdfs

## Como Executar

1.  **Abrir no Google Colab:**
    * Abra um novo notebook no [Google Colab](https://colab.research.google.com/).
    * Copie o arquivo do Jupyter Notebook deste repositorio: CRIACOMP_Assistente_Virtual...

***OS PASSOS SEGUINTES SÃO EXECUTADOS SEGUINDO A ORDEM DAS CÉLULAS NO ARQUIVO***

2.  **Configurar a Chave da API da OpenAI:**
    * Certifique-se de que você tem uma célula de código que configura a sua chave da API da OpenAI utilizando o `userdata.get('OPENAI_API_KEY')`. Você precisará adicionar sua chave secreta ao `userdata` do Colab (Menu Lateral Esquerdo -> Segredos).

3.  **Carregar os Arquivos PDF:**
    * Crie uma pasta chamada `input_pdfs` na raiz do seu Colab (`/content/input_pdfs`). Você pode fazer isso executando a célula que contém `os.makedirs('/content/input_pdfs', exist_ok=True)`.
    * Faça o upload dos seus arquivos PDF contendo as informações da Coordenação de Extensão para essa pasta `/content/input_pdfs`. Você pode arrastar e soltar os arquivos na aba "Arquivos" à esquerda ou usar código para fazer o upload.

4.  **Executar as Células de Código:**
    * Execute as células de código em sequência, de cima para baixo. Isso irá:
        * Instalar as bibliotecas necessárias (`openai`, `gradio`, `tqdm`).
        * Importar as bibliotecas.
        * Inicializar o cliente da OpenAI com sua chave de API.
        * Criar um vector store na OpenAI.
        * Carregar e processar os arquivos PDF no vector store.
        * Definir a função de resposta do chat (`response_output`).
        * Criar e executar a interface de chat do Gradio.

5.  **Acessar o Chat:**
    * Após a execução da última célula (que executa o Gradio), um link público temporário será gerado. Clique nesse link para abrir a interface do chat no seu navegador.

***Reiterando que os passos acimas são executados seguindo a execução das celulas do arquivo CRIACOMP...***

## Como Usar o Chat

1.  **Digite sua pergunta:** Na caixa de texto na parte inferior da interface do chat, digite sua pergunta sobre a Coordenação de Extensão do CIn/UFPE.
2.  **Envie a pergunta:** Pressione Enter ou clique no botão de enviar.
3.  **Leia a resposta:** A resposta do assistente virtual aparecerá na tela.
4.  **Continue a conversa:**

## Observações Importantes

* **Link Temporário do Gradio:** O link gerado pelo Gradio é temporário e pode expirar após um certo período de inatividade.
