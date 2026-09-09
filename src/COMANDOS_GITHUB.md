# Comandos para crear y subir el repositorio a GitHub

## 1. Descomprimir el ZIP

Ubicarse en la carpeta del proyecto.

## 2. Inicializar Git

```bash
git init
git branch -M main
git add .
git commit -m "feat: entrega inicial arquitectura Deezer"
```

## 3. Crear el repositorio en GitHub

Nombre sugerido:

```text
arquitectura-software-deezer
```

No marcar "Add a README" si ya se está usando este repositorio local.

## 4. Conectar remoto

Reemplazar `USUARIO` por el usuario u organización de GitHub:

```bash
git remote add origin https://github.com/USUARIO/arquitectura-software-deezer.git
git push -u origin main
```

## 5. Crear rama develop

```bash
git checkout -b develop
git push -u origin develop
```

## 6. Ramas por integrante

Ejemplo:

```bash
git checkout develop
git checkout -b docs/c4-contexto
git push -u origin docs/c4-contexto
```

## 7. Reglas recomendadas

- No trabajar directamente sobre `main`.
- Crear Pull Request.
- Al menos un compañero revisa el PR.
- Commits claros:
  - `docs: agrega diagrama C4 de contexto`
  - `docs: registra ADR de CDN`
  - `fix: corrige relaciones del diagrama de contenedores`
