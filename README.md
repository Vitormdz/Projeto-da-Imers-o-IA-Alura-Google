# Assistente de Busca de Emprego com Gemini e Google ADK

Este projeto em Python utiliza os modelos Gemini do Google e o framework ADK (Agent Development Kit) para criar um sistema de busca de empregos inteligente e automatizado. O sistema é composto por quatro agentes distintos que trabalham em conjunto para auxiliar na sua busca por uma nova oportunidade de trabalho:

1.  **Agente Buscador de Vagas:** Responsável por pesquisar vagas de emprego na área especificada pelo usuário, utilizando a ferramenta de busca do Google. Ele busca as vagas mais recentes (com no máximo um mês de publicação) e relevantes, incluindo os links para as oportunidades encontradas.

2.  **Agente de Filtragem:** Este agente atua como um recrutador, triando as vagas encontradas pelo Agente Buscador. Com base nas descrições das vagas, ele pesquisa informações adicionais (como benefícios, salários e pré-requisitos) e seleciona as cinco vagas mais relevantes para o usuário.

3.  **Agente Coach de Carreira:** O Coach de Carreira analisa as cinco vagas filtradas e escolhe a que parece mais promissora. Ele aponta os aspectos mais relevantes da vaga selecionada e oferece dicas personalizadas sobre como aumentar as chances de ser contratado, incluindo orientações para a entrevista e os principais tópicos que podem ser abordados.

4.  **Agente Revisor de Qualidade:** Por fim, o Revisor de Qualidade avalia as dicas e orientações geradas pelo Agente Coach. Ele verifica a clareza, concisão, correção e tom do texto. Se o rascunho estiver bem elaborado, ele confirma que está pronto para ser utilizado. Caso contrário, ele aponta os problemas e sugere melhorias.

## Pré-requisitos

Antes de executar o código, você precisará configurar algumas coisas:

* **Conta Google Cloud:** Você precisará de uma conta no Google Cloud para acessar os modelos Gemini.
* **API Key do Google Gemini:** Será necessário obter uma API Key do Google Gemini e configurá-la como um segredo no Google Colab (ou em seu ambiente de desenvolvimento). As instruções no código utilizam `google.colab.userdata` para acessar a chave.

    ```python
    # Configura a API Key do Google Gemini
    import os
    from google.colab import userdata

    os.environ["GOOGLE_API_KEY"] = userdata.get('GOOGLE_API_KEY')
    ```

* **Bibliotecas Python:** As seguintes bibliotecas Python são utilizadas e precisam ser instaladas:

    ```bash
    %pip install -q google-genai
    %pip install -q google-adk
    ```

## Como Usar

1.  **Abra o código no Google Colab (ou em seu ambiente Python).**
2.  **Certifique-se de ter configurado sua API Key do Google Gemini.**
3.  **Execute as células de código em sequência.**
4.  Quando o sistema solicitar, digite a **área de emprego** na qual você está buscando uma vaga e pressione Enter.

    ```
    🚀 Iniciando o Sistema de Busca de vagas de emprego com 4 Agentes 🚀
    ❓ Por favor, digite a ÁREA na qual você deseja encontrar uma vaga:
    ```

5.  O sistema de agentes irá processar sua solicitação, e você verá os resultados de cada agente sendo exibidos na tela:
    * **Resultado do agente 1 (Buscador):** Lista de vagas encontradas e links.
    * **Resultado do agente 2 (Filtrador):** Triagem das vagas mais relevantes com informações adicionais.
    * **Resultado do agente 3 (Coach):** Análise da vaga mais promissora e dicas para a candidatura e entrevista.
    * **Resultado do agente 4 (Revisor):** Avaliação do plano de candidatura.

## Exemplo de Uso

Se você digitar "qa" (Quality Assurance) como a área de busca, o sistema irá procurar vagas de QA, filtrar as melhores opções e fornecer dicas para sua candidatura.

## Observações

* A qualidade dos resultados depende da precisão da área de busca fornecida e da disponibilidade de informações online sobre as vagas.
* O sistema utiliza a data atual para buscar vagas recentes (com no máximo um mês de publicação).
* As buscas são realizadas em português. Para buscar em outros idiomas, pode ser necessário ajustar as instruções dos agentes.
* Este é um exemplo de como agentes de IA podem ser utilizados para auxiliar na busca de emprego. Você pode personalizar e expandir este sistema adicionando mais funcionalidades e agentes.

## Próximos Passos e Melhorias

* Implementar a persistência das preferências do usuário.
* Permitir que o usuário refine os critérios de busca (salário, localização, tipo de contrato, etc.).
* Adicionar um agente para auxiliar na redação de currículos e cartas de apresentação.
* Integrar com plataformas de recrutamento para automatizar a aplicação às vagas.
* Melhorar a capacidade do Agente de Filtragem de analisar documentos (como PDFs de descrição de vagas).
* Permitir que o usuário interaja com os agentes em múltiplas rodadas para refinar os resultados.
  
