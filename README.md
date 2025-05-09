# Gabaritando - Correção de Provas Automatizada

## 📜 Visão Geral do Projeto
O aplicativo foi desenvolvido com o objetivo de automatizar a correção de provas, permitindo que professores cadastrem o gabarito e corrijam as provas dos alunos de maneira simples e eficiente. O aplicativo funciona de forma rápida e prática, utilizando a câmera do dispositivo para escanear os gabaritos e calcular a nota automaticamente.

### 🎯 Atores do Sistema
**Professor**: É o único usuário do sistema, responsável por cadastrar o gabarito, escanear gabaritos dos alunos e visualizar os resultados.

### 📝 Casos de Uso

**UC01 - Cadastrar Gabarito**  
**Ator Primário**: Professor  
**Descrição**: O professor insere manualmente as respostas corretas de cada questão.  
**Fluxo Principal**:
1. O professor acessa a aba "Cadastrar Gabarito".
2. Insere o número de questões.
3. Digita as alternativas corretas (A, B, C, D...).
4. O sistema salva o gabarito localmente ou na nuvem.

**UC02 - Escanear Gabarito do Aluno**  
**Ator Primário**: Professor  
**Descrição**: O professor abre a câmera do celular, aponta para o gabarito do aluno, e o sistema reconhece automaticamente as marcações.  
**Fluxo Principal**:
1. O professor acessa a aba “Corrigir Prova”.
2. A câmera é aberta.
3. O professor aponta para o gabarito do aluno.
4. O app processa a imagem e identifica as marcações.
5. O sistema compara com o gabarito cadastrado.

**UC03 - Exibir Resultado**  
**Ator Primário**: Professor  
**Descrição**: Após o escaneamento, o sistema exibe a nota do aluno.  
**Fluxo Principal**:
1. O app calcula a pontuação com base nos acertos.
2. Exibe a nota no formato "X/Y".

## 🛠 Tecnologias Utilizadas
- **Flutter**: Framework para desenvolvimento de aplicativos móveis.
- **OpenCV**: Para detectar áreas marcadas (círculos, quadrados, marcações).
- **Tesseract OCR** (opcional): Se o gabarito do aluno tiver letras ou símbolos legíveis.
- **SQLite**: Armazenamento local dos gabaritos e resultados.

## 🚀 Requisitos Funcionais
- **RF01**: O sistema deve permitir o cadastro de um gabarito manualmente.
- **RF02**: O sistema deve capturar imagens via câmera.
- **RF03**: O sistema deve processar e identificar as respostas do aluno.
- **RF04**: O sistema deve comparar as respostas com o gabarito.
- **RF05**: O sistema deve exibir a nota do aluno ao professor.

## ⚙ Requisitos Não Funcionais
- **RNF01**: O app deve funcionar offline após o cadastro do gabarito.
- **RNF02**: A leitura da câmera deve ocorrer em no máximo 3 segundos.
- **RNF03**: O sistema deve ser compatível com Android 8+.
- **RNF04**: O tempo de resposta da correção deve ser inferior a 2 segundos após a captura da imagem.

## 📱 Considerações de Usabilidade
- O app deve guiar o professor com sugestões visuais para posicionamento correto da câmera.
- Caso a leitura falhe, o app deve permitir tentar novamente ou inserir respostas manualmente (opcional).
- Interface limpa e fácil de usar.

## 📈 Possíveis Extensões Futuras
- Exportar relatórios em PDF.
- Leitura em tempo real (sem precisar tirar foto).

## 🤔 Exemplificação do Projeto
Imagine um professor que acabou de aplicar uma prova em sala de aula. Normalmente, ele precisaria corrigir as provas manualmente, o que leva tempo e exige muita atenção. Com o nosso app, o professor pode cadastrar o gabarito da prova e, depois, usar a câmera do celular para escanear o gabarito do aluno. O sistema reconhece automaticamente as respostas e exibe a nota rapidamente.

Além disso, o app pode funcionar offline, o que é útil para escolas com acesso limitado à internet. No futuro, pretendemos adicionar funcionalidades como exportação de relatórios em PDF e leitura em tempo real das respostas.

---

# Estrutura do Projeto

Este projeto foi organizado de forma a manter o código modular e fácil de manter. Abaixo está uma explicação detalhada de cada pasta e sua função dentro do projeto.

## 📁 Estrutura do Projeto

### 📁 `assets/`
Contém arquivos estáticos utilizados no aplicativo, como imagens, ícones, fontes e outros recursos gráficos.

- **Exemplo de subpastas**:
  - `assets/images/` - Imagens utilizadas no app.
  - `assets/fonts/` - Fontes personalizadas.
  - `assets/icons/` - Ícones customizados.

### 📁 `lib/`
Pasta principal onde o código-fonte do aplicativo reside. Dentro dela, o código é modularizado em várias subpastas conforme as funcionalidades do app.

#### 📁 `lib/componentes/`
Armazena **widgets reutilizáveis** e componentes UI que podem ser usados em várias telas do aplicativo. Isso inclui botões customizados, campos de texto, indicadores de carregamento, entre outros.

- **Exemplo**:
  - `custom_button.dart` - Um botão customizado com estilo próprio.
  - `custom_input.dart` - Campo de entrada de texto com validações e estilos.

#### 📁 `lib/modelo/`
Armazena **modelos de dados** que representam as estruturas do sistema. Exemplos típicos incluem classes como `Aluno`, `Resultado`, entre outras.

- **Exemplo**:
  - `gabarito.dart` - Modelo que representa o gabarito.
  - `aluno.dart` - Modelo que representa um aluno.
  - `resultado.dart` - Modelo para armazenar o resultado da prova de um aluno.

#### 📁 `lib/telas/`
Contém as **telas do aplicativo**. Cada tela geralmente será um arquivo que define o layout e a lógica de controle daquela parte específica do app.

- **Exemplo**:
  - `cadastro_gabarito.dart` - Tela onde o professor insere o gabarito.
  - `escanear_gabarito.dart` - Tela para escanear o gabarito do aluno.

#### 📁 `lib/main/`
Esta pasta contém o ponto de **entrada** do aplicativo, onde são feitas as configurações iniciais e a inicialização das dependências principais do app.

- **Exemplo**:
  - `main.dart` - Ponto de entrada principal do aplicativo, onde a aplicação é configurada e executada.

### 📁 `database/`
Contém a **lógica de manipulação de banco de dados**, seja local ou remoto. O banco de dados pode ser usado para armazenar dados como o gabarito e os resultados das provas.

- **Exemplo**:
  - `local_db.dart` - Manipulação do banco de dados local, como o SQLite.

### 📁 `services/`
Armazena **serviços especializados** que fornecem funcionalidades específicas do aplicativo, como integração com a câmera, reconhecimento de imagens, ou interação com APIs externas.

- **Exemplo**:
  - `camera_service.dart` - Serviço para gerenciar a câmera do dispositivo.
  - `ocr_service.dart` - Serviço para integrar a tecnologia de OCR (Reconhecimento Óptico de Caracteres).

### 📁 `utils/`
Contém **funções auxiliares** e utilitárias que são utilizadas em várias partes do código. Essas funções geralmente não pertencem a uma lógica específica de negócio ou de UI, mas são essenciais para a implementação do app.

- **Exemplo**:
  - `image_processing.dart` - Funções auxiliares para processamento de imagens.
  - `result_calculation.dart` - Funções para cálculo da nota do aluno com base nas respostas.

---

Essa estrutura foi projetada para garantir que o código permaneça **bem organizado**, **modular** e **escala** facilmente conforme o projeto cresce. Cada pasta tem um objetivo específico, facilitando a navegação e a manutenção do código.

---

## 📚 Dicas de Git

Se você está começando a usar Git ou precisa de algumas dicas úteis, consulte [Dicas de Git](https://kovokar.github.io/PPI-2025.1/git.html).



