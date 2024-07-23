# pwe1

<!DOCTYPE html>.
<html lang="en">: Elemento raiz HTML com atributo de idioma definido como inglês.
<head>: Contém metadados e referências para recursos externos.
Meta tags: Especificam a codificação de caracteres, compatibilidade com o navegador e configuração de viewport para dispositivos móveis.
<title>: Define o título da página exibido na barra de título do navegador.
<link rel="stylesheet">: Referências para folhas de estilo CSS locais e externas (Font Awesome).
<script src="js/scripts.js" defer></script>: Importa um arquivo JavaScript externo com o atributo defer, que adia a execução do script até que o documento HTML seja completamente analisado.

<div class="todo-container">: Container principal que envolve todo o conteúdo da aplicação.
<header>: Cabeçalho da página que inclui o título principal.
Formulário #todo-form:
Permite aos usuários adicionar novas tarefas. Contém um campo de entrada (<input>) e um botão de envio (<button>).
Formulário #edit-form:
Inicialmente oculto (class="hide"), é usado para editar tarefas existentes. Contém um campo de entrada e botões de confirmação e cancelamento.
<div id="toolbar">:
Contém ferramentas para pesquisa e filtragem de tarefas.
#search:
Formulário com campo de entrada para busca e botão de limpeza.
#filter:
Selecionador <select> para filtrar tarefas por status ("Todos", "Feitos", "A fazer").
<div id="todo-list">:
Lista de tarefas.
div.todo:
Cada tarefa é representada por um elemento <div> com classe todo.
<h3>: Título da tarefa.
Botões dentro de <div class="todo">:
.finish-todo: Marca a tarefa como concluída.
.edit-todo: Permite editar a tarefa.
.remove-todo: Remove a tarefa da lista.

java 
API_URL
Seleção de Elementos: Variáveis que armazenam referências a elementos do DOM para interação e manipulação, como formulários, inputs, botões e a lista de tarefas.
getTodos(): Realiza uma requisição assíncrona para obter todas as tarefas da API. Limpa o conteúdo atual da todoList e adiciona cada tarefa ao DOM usando a função addTodoToDOM().
function addTodoToDOM(todo)
ddTodoToDOM(todo): Cria um elemento <div> para representar uma tarefa na interface. Inclui botões para marcar como concluída, editar e remover a tarefa. Os botões utilizam funções inline para lidar com suas respectivas ações.
async function addTodoHandler(e)
addTodoHandler(e): Lida com a adição de uma nova tarefa quando o formulário todoForm é enviado. Envia uma requisição POST para a API para criar uma nova tarefa com o título fornecido. Após a criação bem-sucedida, atualiza a interface adicionando a nova tarefa.
function cancelEditHandler()
cancelEditHandler(): Cancela o modo de edição de uma tarefa, resetando o currentEditingId para null e alternando a visibilidade dos formulários de edição e adição (editForm e todoForm).
async function submitEditHandler(e)
submitEditHandler(e): Submete a edição de uma tarefa quando o formulário de edição é enviado. Envia uma requisição PUT para atualizar os dados da tarefa especificada na API. Após a atualização bem-sucedida, recarrega a lista de tarefas e cancela o modo de edição.
Funções Auxiliares e Event Listeners
Funções como saveTodo, toggleForms, updateTodo, getSearchedTodos, filterTodos: Lidam com operações específicas na interface do usuário, como adicionar uma tarefa, alternar entre formulários, atualizar o título de uma tarefa, realizar buscas e filtrar tarefas exibidas.
Event Listeners: Respondem a eventos como envios de formulários, cliques em botões e alterações em campos de entrada para executar as funções apropriadas.
Local Storage
Funções como getTodosLocalStorage, loadTodos, saveTodoLocalStorage, removeTodoLocalStorage, updateTodoStatusLocalStorage, updateTodoLocalStorage são utilizadas para armazenar e recuperar dados localmente no navegador do usuário, permitindo persistência das tarefas mesmo após recarregar a página.
getTodos() é chamado inicialmente para carregar as tarefas da API ao iniciar a página.
loadTodos() carrega as tarefas armazenadas localmente para manter a consistência entre os dados da interface e os dados armazenados no navegador.

css

*: Reseta o padding e margin de todos os elementos, e define box-sizing: border-box para que o padding e border não alterem o tamanho total do elemento.
body: Define o fundo do corpo com um gradiente linear azul (#0000ff para #00ffff).
Estilos de Botão
Estiliza os botões com fundo, cor, borda, padding, tamanho de fonte e comportamento de hover. Os ícones dentro dos botões (representados por <i>) herdam estilos específicos, mudando de cor no hover.
Estilos de Inputs e Selects
Define padding para inputs e selects.
Classes de Utilidade
Define padding para inputs e selects.
Utilizada para esconder elementos (display: none;).
Estilos do Container Principal
Estiliza o container principal (todo-container) da aplicação de lista de tarefas, incluindo margens, padding, cor de fundo e borda arredondada. O cabeçalho (header) dentro do container também recebe estilos específicos, como alinhamento de texto, padding e borda inferior.
Estilos dos Formulários
Estiliza os formulários (todo-form e edit-form), incluindo padding, bordas e margens. Define estilos para os parágrafos dentro dos formulários, a classe .form-control (utilizada para o layout de campos de formulário), inputs e botão de cancelar edição.
Estilos da Barra de Ferramentas
Estiliza a barra de ferramentas (toolbar) da aplicação, que inclui padding, bordas, alinhamento e layout dos elementos. Define estilos para títulos (h4), área de pesquisa (search) com borda lateral, inputs e selects de filtro.
Estilos da Lista de Tarefas
Estiliza os itens individuais da lista de tarefas (todo). Define layout flexível, espaçamento, padding, bordas e transição para animações. Estiliza o texto (h3) das tarefas e o comportamento visual das tarefas concluídas (done), alterando o fundo e o estilo do texto.


