# File_Manager
 O `File_Manager` é uma aplicação em C++ com interface gráfica (GUI) criada com Qt Desing, que permite ao usuário monitorar alterações em um diretório, como adição, exclusão, modificação e renomeação de arquivos e pastas. O aplicativo exibe essas informações e permite exportar os dados para arquivos CSV e TXT, além de armazenar um histórico das alterações em um banco de dados SQLite.

## Funcionalidades

- **Seleção de Diretório**: Escolha um diretório para monitoramento.
- **Análise de Diretório**: Analisa as mudanças (arquivos adicionados, modificados, renomeados e excluídos).
- **Exportação de Dados**: Exporta as informações de mudanças para arquivos CSV ou TXT.
- **Limpeza de Dados**: Limpa o histórico atual de mudanças.

## Documentação para DirectoryAnalyzer.cpp e DirectoryAnalyzer.h

**Descrição geral:**

Este código implementa uma interface gráfica para analisar diretórios e exportar as alterações (criação, modificação e deleção de arquivos/diretórios) para arquivos CSV ou TXT. O programa utiliza um banco de dados SQLite para armazenar as informações das alterações.

**Componentes:**

* **DirectoryAnalyzer.cpp:** Implementa a lógica principal da aplicação, incluindo a interface com o usuário (Qt), o gerenciamento do banco de dados (SQLite) e as funções para analisar diretórios e exportar dados.
* **DirectoryAnalyzer.h:** Define a classe `DirectoryAnalyzer` e seus métodos públicos e privados.

**Classes:**

* **DirectoryAnalyzer:**
    * Esta classe é responsável por toda a funcionalidade da aplicação.
    * Ela gerencia a interface gráfica (Qt), o banco de dados SQLite e as operações de análise de diretórios e exportação de dados.

**Funções:**

* **initUI():** Inicializa a interface gráfica com labels, botões e a tabela para exibir as alterações.
* **create_button(const QString &text):** Cria um botão personalizado com tamanho e fonte definidos.
* **init_db():** Conecta ao banco de dados SQLite e cria a tabela `changes` (se ela não existir).
* **select_directory():** Abre um diálogo para selecionar um diretório e atualiza o estado interno.
* **scan_directory(const QString &directory):** Examina um diretório e retorna um mapa contendo informações sobre os arquivos e diretórios.
* **analyze_directory():** Analisa o diretório selecionado, verifica alterações e registra no banco de dados.
* **load_db_content():** Carrega os dados do banco de dados e exibe na tabela.
* **export_to_csv():** Exporta as alterações para um arquivo CSV.
* **export_to_txt():** Exporta as alterações para um arquivo TXT.
* **clear_data():** Limpa a tabela e o banco de dados.
* **format_time(qint64 timestamp):** Formata um timestamp para o formato "yyyy-MM-dd HH:mm:ss".

**Observações:**

* O código comentado `//export_to_xlsx()` indica uma funcionalidade desabilitada para exportar dados para Excel (provavelmente devido à falta da biblioteca `libxl`).
* Os caminhos para o banco de dados e ícones estão definidos diretamente no código e podem ser alterados conforme a necessidade.

## Documentação para File_Manager.cpp e CMakeLists.txt

**File_Manager.cpp:**

* Este arquivo é o ponto de entrada da aplicação.
* Ele cria uma instância da classe `DirectoryAnalyzer` e a exibe na tela.

**CMakeLists.txt:**

* Define o projeto como `File_Manager`.
* Configura o padrão C++ para 17.
* Procura pela biblioteca Qt6 com os componentes Core, Gui, Widgets e Sql.
* Habilita o gerador automático de código Qt (MOC).
* **Comentado:** Define o diretório de instalação da biblioteca `libxl` (necessária para exportar para Excel, mas não utilizada no código atual).
* Inclui o diretório de cabeçalhos do `libxl` (somente se for utilizado).
* Define o caminho para o Qt instalado.
* Define o executável principal (`File_Manager`) e compila os arquivos fonte.
* Vincula as bibliotecas Qt e, opcionalmente, a biblioteca `libxl` (se for utilizada).
* Define as flags de compilação específicas para Windows.


## Considerações finais

Esta documentação fornece uma visão geral do código e explica a funcionalidade das classes e funções principais. Para uma documentação mais detalhada, seria interessante incluir comentários explicativos dentro do código fonte, especialmente para funções complexas ou trechos críticos.
