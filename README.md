# AirJobs Templates

Ce repository contient les templates de steps et workflows pour AirJobs/Cadriciel Studio.

## Structure

```
airjobs-templates/
├── steps/           # Définitions des steps disponibles
│   ├── shell.json
│   ├── python.json
│   ├── ffmpeg.json
│   └── ...
├── workflows/       # Templates de workflows pré-configurés
│   ├── hello-world.json
│   ├── image-pipeline.json
│   └── ...
└── README.md
```

## Format des Steps

Chaque step est défini dans un fichier JSON avec la structure suivante :

```json
{
  "id": "shell",
  "name": "Shell Script",
  "description": "Execute shell commands with Alpine Linux",
  "image": "alpine:latest",
  "icon": "terminal",
  "color": "#4ade80",
  "defaultCommands": ["echo 'Hello World'"],
  "produces": [],
  "env": {}
}
```

### Champs

| Champ | Type | Description |
|-------|------|-------------|
| `id` | string | Identifiant unique du step |
| `name` | string | Nom affiché dans l'interface |
| `description` | string | Description du step |
| `image` | string | Image Docker à utiliser |
| `icon` | string | Icône (shell, python, video, image, database, cloud, custom) |
| `color` | string | Couleur hex pour l'interface |
| `defaultCommands` | string[] | Commandes par défaut |
| `produces` | object[] | Outputs produits par le step |
| `env` | object | Variables d'environnement |
| `examples` | object[] | Exemples d'utilisation (optionnel) |

## Format des Workflows

```json
{
  "id": "hello-world",
  "name": "Hello World",
  "description": "Simple workflow example",
  "stages": [
    {
      "name": "say-hello",
      "image": "alpine:latest",
      "commands": ["echo 'Hello {{input.name}}'"]
    }
  ],
  "input": [
    { "name": "name", "type": "string", "default": "World" }
  ]
}
```

## Icônes disponibles

- `shell` / `terminal` - Terminal/Shell
- `python` - Python
- `javascript` - JavaScript/Node.js
- `video` - FFmpeg/Video
- `image` - ImageMagick/Images
- `database` - PostgreSQL/Databases
- `cloud` - S3/Cloud storage
- `custom` - Custom steps

## Contribution

Pour ajouter un nouveau step ou workflow :

1. Créer un fichier JSON dans le dossier approprié
2. Respecter le format décrit ci-dessus
3. Tester localement
4. Soumettre une Pull Request

## License

MIT
