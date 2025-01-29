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

## Enable Module
This endpoint shoudl be used to enable a module using it's identifier. You'll replace `{identifier}` with the module's identifier you want to enable. 

<aside class="notice">
Performing this will not execute the module migration if they are needed. By accessing NexoPOS, the migration will be performed.
</aside>


<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/modules/{identifier}/enable</div>
    </div>
</div>

> Response

```json
{
  "status": "success",
  "message": "The module has correctly been enabled.",
  "data": {
    "code": "module_enabled",
    "module": {
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
      "enabled": false,
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
      "migrations": [],
      "all-migrations": [
        "NsGastro/Migrations/UpdateToV5Migration.php"
      ]
    },
    "migrations": []
  }
}
```

## Disable Module

This endpoint is used to disable a module using it's identifier. You'll replace `{identifier}` by the module's identifer you want to disable. 

<aside class="notice">
Note that this method can't be used as way around to disable a module in case you're not able to access the dashboard.
</aside>

Please refer to [this guide](https://my.nexopos.com/en/documentation/troubleshooting/how-to-disable-a-module-without-dashboard-access-on-nexopos-4-x) to disable a module when you're locked out of the dashboard.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/modules/{identifier}/disable</div>
    </div>
</div>

> Response 

```json
{
  "status": "success",
  "code": "module_disabled",
  "message": "The Module has been disabled.",
  "module": {
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
  }
}
```

## Remove Module

This endpoint will remove the module from NexoPOS using the provided identifier. This will also delete all tables that might have been created by the module. You'll replace `{identifier}` with the module's identifier.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/modules/{identifier}/delete</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]",
    "code": "[string]",
    "module": "{}"
}
```

## Upload Module

Use this endpoint to upload a module as a zip file. This endpoint will perform install and update if necessary.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/modules</div>
    </div>
</div>

> Request

```json
{
    "module": "[zip binary]"
}
```

> Response

```json
{
    "status": "[error|success]",
    "message": "[string]"
}
```