# 🚀 Configuração TypeScript + Node.js (Guia Rápido)

Este guia explica como configurar um projeto **Node.js com TypeScript**, utilizando **ESM/ESNext**, **ts-node** e **nodemon** para desenvolvimento ágil e moderno.

---

## 📦 Inicialização do Projeto

```bash
npm init -y
```

Cria um arquivo `package.json` com as configurações básicas do projeto.

---

## ⚙️ Instalação das Dependências

### Dependências de Desenvolvimento

```bash
npm install -D typescript
npm install ts-node
npm install nodemon
```

- **typescript** → Compilador oficial do TypeScript.  
- **ts-node** → Permite executar arquivos `.ts` diretamente, sem precisar compilar antes.  
- **nodemon** → Reinicia automaticamente o servidor a cada alteração no código.

---

## 🧠 Inicializando o TypeScript

Crie o arquivo de configuração padrão do TypeScript:

```bash
npx tsc --init
```

---

## 🧩 Configuração do `tsconfig.json`

Exemplo de configuração otimizada para projetos Node.js modernos:

```json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "nodenext",
    "rootDir": "./src",
    "outDir": "./dist",

    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": ["src", "server.ts"],
  "exclude": ["node_modules", "dist"]
}
```

---

## 🧱 Explicação dos principais campos

| Propriedade | Descrição |
|--------------|------------|
| `target` | Define para qual versão do ECMAScript o código será convertido (ex: `esnext`, `es2020`, `es2025`). |
| `module` | Define o sistema de módulos usado: `commonjs`, `esnext`, ou `nodenext`. |
| `rootDir` | Diretório onde o código fonte está localizado. |
| `outDir` | Diretório onde os arquivos compilados `.js` serão gerados. |
| `strict` | Habilita a verificação rigorosa de tipos. |
| `esModuleInterop` | Permite usar `import` em libs antigas que usam `require()`. |
| `skipLibCheck` | Ignora verificação de tipos de pacotes externos. |
| `forceConsistentCasingInFileNames` | Evita erros com diferença de maiúsculas/minúsculas nos imports. |

---

## 🧭 Tipos de Módulos

| Módulo | Descrição | Importação / Exportação |
|---------|------------|-------------------------|
| `commonjs` | Padrão antigo do Node.js | `require` / `module.exports` |
| `esnext` | Usa `import`/`export` moderno | `import express from 'express'` |
| `nodenext` | Suporte híbrido (CommonJS + ESM) conforme o Node.js atual | Automático |

---

## 🌐 Padrões ECMAScript (ES)

O **ECMAScript** é o padrão que define o JavaScript.  
Mais detalhes em: [ECMA-262 Standard](https://ecma-international.org/publications-and-standards/standards/ecma-262/)

Exemplo:

```json
"target": "es2025",
"module": "nodenext"
```

Isso garante compatibilidade com os recursos mais recentes do JS no Node.js.

---

## ⚡ Scripts Recomendados no `package.json`

```json
"scripts": {
  "start": "node dist/server.js",
  "dev": "nodemon --exec ts-node src/server.ts",
  "build": "tsc"
}
```

- `npm run dev` → Executa em modo desenvolvimento.  
- `npm run build` → Compila o TypeScript para JavaScript.  
- `npm start` → Roda o código compilado.

---

## 📁 Estrutura de Pastas Sugerida

```
project/
│
├── src/
│   ├── server.ts
│   └── ...
│
├── dist/
│
├── tsconfig.json
├── package.json
└── README.md
```

---

## 📚 Referências

- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)  
- [tsconfig.json Documentation](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)  
- [ECMAScript Official Standard](https://ecma-international.org/publications-and-standards/standards/ecma-262/)

---

### ✨ Autor

**Carlos Jaime**  
Desenvolvedor Full Stack & Professor de Desenvolvimento Web  
📎 [GitHub](https://github.com/carlosjaimeandrade)
