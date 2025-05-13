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



## 📚 Dicas de Git

Se você está começando a usar Git ou precisa de algumas dicas úteis, consulte [Dicas de Git](https://kovokar.github.io/PPI-2025.1/git.html).



