# 🎲 Sorteador de Números - Automação Grunt

![Status](https://img.shields.io/badge/Status-Finalizado-green)
![Grunt](https://img.shields.io/badge/Build_Tool-Grunt-fba919?logo=grunt&logoColor=white)
![LESS](https://img.shields.io/badge/Style-LESS-1d365d?logo=less&logoColor=white)
![JavaScript](https://img.shields.io/badge/Code-JavaScript-yellow?logo=javascript&logoColor=white)

> Uma aplicação interativa para realizar sorteios, desenvolvida com foco na arquitetura de projeto e automação de tarefas repetitivas.

## 🎯 Motivação e Propósito

A criação de aplicações web modernas exige performance. O propósito deste projeto foi criar uma ferramenta funcional (um sorteador) enquanto se resolvia um problema técnico de desenvolvimento: a necessidade de compilar e otimizar arquivos manualmente.

Este projeto implementa o **Grunt.js** para automatizar o fluxo de trabalho, garantindo que o CSS final seja gerado a partir do LESS e que o JavaScript seja comprimido para carregamento rápido, simulando um ambiente de deploy profissional.

## 🖼️ Demonstração Visual

https://sorteador-grunt-two-smoky.vercel.app

## 🛠️ Tecnologias Utilizadas

A stack tecnológica combina lógica de interface com ferramentas de build:

* **[Grunt](https://gruntjs.com/):** Task Runner responsável pela orquestração do build.
    * `grunt-contrib-less`: Compilação de estilos.
    * `grunt-contrib-uglify`: Minificação de scripts.
    * `grunt-contrib-watch`: Monitoramento em tempo real.
* **[LESS](https://lesscss.org/):** Pré-processador CSS para estilização modular (uso de variáveis e aninhamento).
* **[JavaScript (ES6+)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript):** Lógica matemática para geração do número aleatório (`Math.random`).
* **[HTML5](https://developer.mozilla.org/pt-BR/docs/Web/HTML):** Estrutura semântica.

## ✨ Funcionalidades

1.  **Sorteio Aleatório:** O usuário define um número máximo e o sistema retorna um valor aleatório entre 1 e o máximo definido.
2.  **Validação de Input:** Impede o sorteio caso o campo esteja vazio.
3.  **Pipeline de Build Automatizado:**
    * Transpilação de LESS para CSS.
    * Compressão de código JavaScript (Uglify).
    * Monitoramento de arquivos (Watch) para desenvolvimento ágil.

## 📦 Instalação e Configuração

Este projeto depende do Node.js para rodar as tarefas de automação.

### Pré-requisitos
* **Node.js** e **NPM** instalados.
* **Git** instalado.

### Passo a Passo

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/DouglassenG/sorteador_grunt.git](https://github.com/DouglassenG/sorteador_grunt.git)
    ```

2.  **Acesse o diretório:**
    ```bash
    cd sorteador_grunt
    ```

3.  **Instale as dependências:**
    Este comando é crucial. Ele lerá o `package.json` e baixará todos os plugins do Grunt necessários para a pasta `node_modules`.
    ```bash
    npm install
    ```

4.  **Execute o Projeto (Build):**
    Para rodar as tarefas de compilação e iniciar o "Watch" (monitoramento):
    ```bash
    npm run grunt
    # Ou se tiver o CLI global:
    grunt
    ```

## 💻 Uso e Exemplos

### Uso da Aplicação (Usuário Final)
1.  Abra o arquivo `index.html` no navegador.
2.  Digite um número máximo (ex: 100).
3.  Clique em "Sortear número".
4.  O resultado aparecerá na tela instantaneamente.

### Uso do Código (Desenvolvedor)
A estrutura separa o código fonte (`src`) do código compilado.

* **Entrada:** Edite os arquivos em `src/styles/main.less` ou `src/scripts/main.js`.
* **Processamento:** O Grunt detecta a mudança.
* **Saída:** O Grunt atualiza automaticamente os arquivos na pasta `dist/` ou `dev/`.

**Exemplo de Configuração (Gruntfile.js):**
```javascript
// Trecho da configuração de minificação
uglify: {
    target: {
        files: {
            'dist/scripts/main.min.js': ['src/scripts/main.js']
        }
    }
}
