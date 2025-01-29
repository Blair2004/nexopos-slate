# Modules

This section allows you to interact with existing module.

## List Modules

Use this endpoint to receive a list of available modules.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/modules</div>
    </div>
</div>

> Response

```json
{
  "modules": {
    "NsGastro": {
      "namespace": "NsGastro",
      "version": "5.3",
      "author": "Blair Jersyer",
      "name": "Gastro - Restaurant Extension",
      "description": "Gastro provides a restaurant features on top of NexoPOS to ease restaurant management.",
      "core": {
        "min-version": "5.2.6",
        "max-version": "5.3.0"
      },
      "recommends": {
        "dependency": "Nexo Print Adapter"
      },
      "requires": [],
      "files": [
        ".gitignore",
        "NsGastroModule.php",
        "README.md",
        "commands.txt",
        "config.xml",
        "index.php",
        "package-lock.json",
        "package.json",
        "phpunit.ci.xml",
        "phpunit.xml",
        "phpunit.xml.bak",
        "postcss.config.cjs",
        "tailwind.config.cjs",
        "todo",
        "tsconfig.json",
        "vite.config.js"
      ],
      "api-file": "/var/www/html/default/modules/NsGastro/Routes/api.php",
      "composer-installed": false,
      "controllers-path": "/var/www/html/default/modules/NsGastro/Http/Controllers",
      "controllers-relativePath": "NsGastro/Http/Controllers",
      "enabled": true,
      "has-languages": true,
      "lang-relativePath": "modules/NsGastro/Lang",
      "index-file": "/var/www/html/default/modules/NsGastro/NsGastroModule.php",
      "path": "/var/www/html/default/modules/NsGastro/",
      "relativePath": "modules/NsGastro/",
      "requires-composer": false,
      "routes-file": "/var/www/html/default/modules/NsGastro/Routes/web.php",
      "views-path": "/var/www/html/default/modules/NsGastro/Resources/Views",
      "views-relativePath": "modules/NsGastro/Views",
      "autoloaded": false,
      "entry-class": "Modules\\NsGastro\\NsGastroModule",
      "providers": [
        "NsGastro/Providers/ModuleServiceProvider.php"
      ],
      "actions": [],
      "filters": [],
      "commands": [],
      "psr-4-compliance": true,
      "langFiles": {
        "ar": "NsGastro/Lang/ar.json",
        "de": "NsGastro/Lang/de.json",
        "en": "NsGastro/Lang/en.json",
        "es": "NsGastro/Lang/es.json",
        "fr": "NsGastro/Lang/fr.json",
        "it": "NsGastro/Lang/it.json",
        "nl": "NsGastro/Lang/nl.json",
        "pt": "NsGastro/Lang/pt.json",
        "sq": "NsGastro/Lang/sq.json",
        "tr": "NsGastro/Lang/tr.json",
        "vi": "NsGastro/Lang/vi.json"
      },
      "migrations": [],
      "all-migrations": [
        "NsGastro/Migrations/UpdateToV5Migration.php"
      ]
    },
  },
  "total_enabled": 1,
  "total_disabled": 0,
  "total_invalid": 0
}
```