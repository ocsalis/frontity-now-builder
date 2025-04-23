# 🚀 Frontity | Vercel Builder

## ⭐ Requirement (23-04-2025):
- node: ">=22.x"
- npm:  ">=11.0.0"
- yarn: ">=1.22.0"

## ⭐ Intégration Frontity
Dans `vercel.json` à la racine de votre projet frontity ajouter :
```json
...
  "builds": [
    {
      "src": "package.json",
      "use": "github:ocsalis/frontity-now-builder"
    }
  ]
...
```

## ⭐ Mise à jour version Vercel/Node
1) Regarder les vertion obsolètes: `npm outdated`
2) Mettre à jour les dépendances vercel avec les nouvelles versions: `package.json`
3) Tester le build: `npx tsc`

_______________
© 2025 développement fait avec ❤️ par [Ocsalis](https://ocsalis.com) dans le Cantal
![Ocsalis|200](https://ocsalis.github.io/img/logo_ocsalis.png)