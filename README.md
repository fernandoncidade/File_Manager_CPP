# README (English)

# File_Manager
The `File_Manager` is a C++ application with a graphical user interface (GUI) created with Qt Design, allowing users to monitor changes in a directory, such as the addition, deletion, modification, and renaming of files and folders. The application displays this information and allows data export to CSV and TXT files, as well as storing a history of changes in an SQLite database.

## Features

- **Directory Selection**: Choose a directory to monitor.
- **Directory Analysis**: Analyzes changes (added, modified, renamed, and deleted files).
- **Data Export**: Exports change information to CSV or TXT files.
- **Data Clearing**: Clears the current change history.

## Documentation for DirectoryAnalyzer.cpp and DirectoryAnalyzer.h

**Overview:**

This code implements a graphical interface to analyze directories and export changes (creation, modification, and deletion of files/directories) to CSV or TXT files. The program uses an SQLite database to store information on changes.

**Components:**

* **DirectoryAnalyzer.cpp:** Implements the main application logic, including the user interface (Qt), database management (SQLite), and functions to analyze directories and export data.
* **DirectoryAnalyzer.h:** Defines the `DirectoryAnalyzer` class and its public and private methods.

**Classes:**

* **DirectoryAnalyzer:**
    * This class is responsible for all the functionality of the application.
    * It manages the graphical interface (Qt), SQLite database, and directory analysis and data export operations.

**Functions:**

* **initUI():** Initializes the graphical interface with labels, buttons, and a table to display changes.
* **create_button(const QString &text):** Creates a custom button with specified size and font.
* **init_db():** Connects to the SQLite database and creates the `changes` table (if it does not exist).
* **select_directory():** Opens a dialog to select a directory and updates the internal state.
* **scan_directory(const QString &directory):** Scans a directory and returns a map containing information about files and directories.
* **analyze_directory():** Analyzes the selected directory, checks for changes, and records them in the database.
* **load_db_content():** Loads data from the database and displays it in the table.
* **export_to_csv():** Exports changes to a CSV file.
* **export_to_txt():** Exports changes to a TXT file.
* **clear_data():** Clears the table and the database.
* **format_time(qint64 timestamp):** Formats a timestamp to the format "yyyy-MM-dd HH:mm:ss".

**Notes:**

* The commented code `//export_to_xlsx()` indicates a disabled feature for exporting data to Excel (likely due to the absence of the `libxl` library).
* Paths for the database and icons are directly set in the code and can be modified as needed.

## Documentation for File_Manager.cpp and CMakeLists.txt

**File_Manager.cpp:**

* This file is the entry point of the application.
* It creates an instance of the `DirectoryAnalyzer` class and displays it on the screen.

**CMakeLists.txt:**

* Defines the project as `File_Manager`.
* Sets the C++ standard to 17.
* Finds the Qt6 library with Core, Gui, Widgets, and Sql components.
* Enables the Qt automatic code generation (MOC).
* **Commented:** Sets the installation directory for the `libxl` library (needed for Excel export, but not used in the current code).
* Includes the header directory of `libxl` (only if used).
* Sets the path to the installed Qt.
* Defines the main executable (`File_Manager`) and compiles the source files.
* Links Qt libraries and, optionally, the `libxl` library (if used).
* Defines Windows-specific compilation flags.

## Final Considerations

This documentation provides an overview of the code and explains the functionality of the main classes and functions. For more detailed documentation, it would be helpful to include explanatory comments within the source code, especially for complex functions or critical sections.



# README (Portuguese)

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
