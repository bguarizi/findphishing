# FindPhishing - Detector de sites de Phishing

Este repositório está vinculado ao artigo "Identificação de Ataques de Phishing através de Machine Learning". O artigo foi publicado no Workshop de Trabalhos de Iniciação Científica e de Graduação da 24º edição do Simpósio Brasileiro em Segurança da Informação e de Sistemas Computacionais.

Este trabalho propõe a elaboração de uma ferramenta que utiliza um classificador Random Forest para análise em tempo real das páginas acessadas pelo usuário através do navegador com o intuito de identificar se a página é legítima ou se tem a possibilidade de ser phishing. A ferramenta possui um algoritmo em Python que hospeda o classificador e realiza a análise da URL da página acessada e uma extensão de navegador que executa a coleta dessas URLs e as envia ao código Python.

## Tópicos

- [Instalação](#instalação)
- [Uso](#uso)
- [Métricas](#metricas)

## Instalação

Para instalar o projeto, siga estes passos:

1. Garanta que você possui o Python instalado em sua máquina:

    Abra o terminal e digite: 

    ```bash
    python --version
    ```

    Caso seja retornada a versão do Python, está tudo ok. Caso você não tenha instalado ainda, siga os seguintes passos:

    - Windows ou MacOs:

    Acesse o site oficial:

    ```bash
    https://www.python.org/downloads/
    ```
    E clique no botão para fazer download, depois siga os passos de instalação e volte ao passo inicial para verificar a versão do Python e se certificar de que a instalação foi feita corretamente.

    - Linux:

    Acesse o site oficial e veja qual é a versão atual disponível do Python:

    ```bash
    https://www.python.org/downloads/
    ```

    Atualmente a versão mais recente é a 3.12.4.
    Em seguida, digite o seguinte comando no terminal:

    ```bash
    sudo apt-get install python3.12
    ```

    Troque o '3.12' pela versão mais atualizada.

    Refaça o passo inicial para verificar a versão instalada e garantir que a instalação ocorreu corretamente.

2. Clone o repositório através do comando:

    ```bash
    git clone https://github.com/bguarizi/findphishing.git
    ```

    Acesse o repositório baixado:

    ```bash
    cd findphishing/
    ```

3. Faça a instalação das bibliotecas necessárias:

   Instale o arquivo requirement.txt através do pip com o seguinte comando:

    ```bash
    pip install -r requirements.txt
    ```

4. Faça download do Google Chrome:

    Caso ainda não possua o navegador instalado, siga os passos a seguir para realizar a instalação:

    Acesse o site oficial:

    ```bash
    https://www.google.com/chrome/
    ```

    Escolha o seu sistema operacional e siga os passos de instalação disponibilizados pelo site.

5. Adicione a extensão ao seu navegador Google Chrome:

    Abra seu navegador e acesse:

    ```bash
    chrome://extensions/
    ```

    Clique no botão "Carregar sem compactação" e vá até o caminho da pasta que acabou de clonar do projeto.
    Selecione a pasta "url-collector-extension" e clique em "Abrir".

    Sua extensão já estará funcionando!


## Uso

Após a instalação ter sido realizada corretamente, basta apenas ativar a execução do código em Python:

1. Abra novamente o terminal na pasta do projeto que foi baixado:

    Após estar na pasta em questão, rode o seguinte comando:

    ```bash
    python code_analyse_trafic.py
    ```

    Aguarde até que a tela mostre que o servidor está ativo na porta 5000.

3. Teste seu navegador:

    Abra o Google Chrome e começe a navegar. 
    Serão emitidos alertas em tempo real sobre as páginas que estão sendo acessadas.

OBS1.: Os alertas podem demorar alguns segundos para serem emitidos.

OBS2.: A cada site acessado, um alerta será emitido e você precisará apertar o botão de confirmação.

OBS3: Caso queira desativar os alertas emitidos, basta cancelar a execução do script no terminal e desativar a extensão do navegador acessando novamente "chrome://extensions/" e desativando ou excluindo a extensão.

OBS4.: Caso não tenha sites de phishing para que possa testar, acesse a pasta do projeto em 'findphishing/d_base/phishStats04_07_24.csv'. Este é um arquivo coletado do site da PhishScore no dia 04/07/2024. Levando em consideração que esta não foi uma das bases de dados utilizada no treinamento e teste do classificador, é possível validar as classificações com as URLs contidas nele.

4. Caso queira realizar a coleta atualizada da base de dados da PhishStats para utilização nos testes:

    Acesse o seu navegador e pesquise por:

    ```bash
    https://phishstats.info/
    ```

    Na parte de baixo do site você encontrará o "CSV Feed", clique no botão "Go" e realize o download do arquivo csv contendo as URLs classificadas como phishing pela PhishStats.


## Métricas

Além do código para ser executado, também é disponibilizado o código que mostra os valores finais das métricas do modelo: acurácia, recall, precisão e F1 Score. Além de também mostrar os gráficos de Matriz de Confusão, Validação Cruzada e Coeficiente de Correlação.

Para executá-lo, acesso no terminal a pasta do projeto e digite o seguinte comando:

    ```bash
    python accuracy_metrics_analyse.py
    ```

