# daily-routine-logger


## 環境構築ログ

ルートにworkspace.yamlを作成
```yaml
packages:
  - "packages/*"
```

```bash
# ルートの作成
pnpm init

# biomeのインストール
pnpm add --save-dev --save-exact @biomejs/biome

# バックエンドプロジェクトの作成
mkdir -p packages/backend
cd packages/backend
pnpm init
pnpm add fastify
pnpm add -D typescript @types/node
```

backend用の tsconfig.json を作成
```json
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "outDir": "dist",
    "rootDir": "src",
    "strict": true,
    "module": "commonjs",
    "target": "ES2020",
    "esModuleInterop": true
  },
  "include": ["src"]
}
```

ルートに共通の tsconfig.base.json を作成
```json
{
  "compilerOptions": {
    "strict": true,
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "skipLibCheck": true
  }
}
```
