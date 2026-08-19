# pc-lopal
Repositório p/ armazerar os códigos da aula.

docs: add desafios 1 a 4

# Desafio 1

## O que é a versão 1.0.0?

  

### **O que significa cada um dos três números dessa versão?**

  

O primeiro número significa Major, o segundo Minor, e o terceiro Patch.

  

### **Quem decide como esse número muda e com base em quê?**

  

Líderes técnicos e desenvolvedores do produto;

  

Se o antigo vai parar de funcionar, mudará o primeiro número (Major), se for adicionada formas, telas ou ferramentas, sem estragar o que ja exista, mudará o segundo número (Minor), caso seja apenas a correção de uma falha (bug), mudará o último número (Patch).


# Desafio 2

## dependencies e devDependencies

  

### Qual a diferença entre os dois grupos?

Dependencies são pacotes e bibliotecas necessários para a execução correta do código.

Já devDependencies são pacotes e bibliotecas que não mudam nada no ambiente final, mas que ajudam o dev a criar/organizar o código.

  

### Como você decide em qual grupo colocar uma biblioteca?

  

Use dependencies para Bibliotecas estruturais e componentes visuais (algo que faz parte diretamente do projeto); Use devDependencies para frameworks de teste e compiladores (algo que não faz parte diretamente do projeto, mas que ajuda o desenvolvedor).


# Desafio 3

## Os símbolos ^ e ~ no package.json

  
  

### **O que cada símbolo permite atualizar?**

O ^ - Caret. Permite atualizar somente a versão Minor e Patch, mantendo travada a versão Major.

  

O ~ - Tilde. Permite atualizar somente a versão Patch, mantendo travada a versão Minor e Major.

  

### **O que acontece quando não existe nenhum símbolo?**

  

Quando não se usa nenhum símbolo o pacote fica travado completamente naquela versão, sem atualizar o Major, Minor ou Patch, ou seja, não fará nenhuma atualização automática.

# Desafio 4

## CommonJS e Module (ESM)

### **Qual a diferença entre os dois?**

A principal diferença entre os dois é que o commonJS é um modelo mais antigo, que funciona somente com o nodeJS, já o module é um modelo mais novo, funcionando tanto pele node, tanto pelo próprio navegador

### **Como cada um surgiu?**

Common: em 2009 o javascript funcionava basicamente só no navegador, assim, um grupo de desenvolvedores se juntou para criar um padrão que permitisse rodar o javascript fora do navegador.

Module: Enquanto o node usava CommonJS, os navegadores usavam outras "gambiarras" ou ferramentas externas. O javascript não tinha uma padrão único e oficial. Assim o comitê oficial que cuida da linguagem javascript, decidiu criar uma solução definitiva que funcionasse em qualquer lugar, nascendo o ES Module, em 2015.

Ou seja, commonJS foi uma solução da comunidade pra fazer o javascript rodar fora dos navegadores, já o ES Module foi uma solução oficial criada depois para unificar tudo.

### **Como é a sintaxe de importação e exportação em cada um?**

***Common:***

### Exportar

#### // Exportação Única (Default)

module.exports = function soma(a, b) {

return a + b;

};

#### // Exportação Múltipla (Nomeada)

function soma(a, b) { return a + b; }

function subtrai(a, b) { return a - b; }

module.exports = { soma, subtrai };

### Importar

#### // Importar Exportação Única

const soma = require('./math');

#### // Importar Exportação Múltipla (usando desestruturação)

const { soma, subtrai } = require('./math');

##

***Module:***

### Exportar

#### // Exportação Única (Default)

export default function soma(a, b) {

return a + b;

}

#### // Exportação Múltipla (Nomeada)

export function soma(a, b) { return a + b; }

export function subtrai(a, b) { return a - b; }

### Importar

#### // Importar Exportação Única (não usa chaves e pode renomear)

import soma from './math.js';

#### // Importar Exportação Múltipla (usa chaves { })

import { soma, subtrai } from './math.js';

#### // Importar tudo de uma vez como um objeto

import * as MathUtils from './math.js';

##

### Regra de ouro visual:

**CommonJS** = require() + module.exports

  

**ES Modules** = import + export (requer a extensão .js no caminho no navegador/Node moderno).