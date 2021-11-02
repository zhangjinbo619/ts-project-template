```
# 1.创建ts-project 项目
mkdir ts-project && cd ts-project && npm init -y && npm i typescript -D && npx tsc --init

# 2. 创建项目入口文件
mkdir src && touch src/index.ts 

# 3. 设置 tsconfig.json
{
  "compileOnSave": true,
  "compilerOptions": {
    "target": "ES2018",
    "module": "commonjs",
    "moduleResolution": "node",
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,
    "inlineSourceMap":true,
    "noImplicitThis": true,
    "noUnusedLocals": true,
    "stripInternal": true,
    "pretty": true,
    "declaration": true,
    "outDir": "lib",
    "baseUrl": "./",
    "paths": {
      "*": ["src/*"]
    }
  },
  "exclude": [
    "lib",
    "node_modules"
  ]
}

# 4. node.js 的类型定义包
npm i @types/node -D

# 5. 开发环境实时编译
 npm i ts-node-dev -D

# 6. 在 package.json 的 scripts 中增加如下内容
{
  "scripts": {
    "dev:comment": "启动开发环境",
    "dev": "ts-node-dev --respawn --transpile-only src/index.ts"
  }
}

#7. eslint检查 (使用社区标准方案)
npm install --save-dev eslint-config-standard eslint-plugin-promise eslint-plugin-import eslint-plugin-node

 
```