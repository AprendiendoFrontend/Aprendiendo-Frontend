## Sesión 2 - Configura y personaliza tu entorno

#### Personaliza tu Prompt (PS1)
ZSH ya trae de serie un prompt muy potente. Aunque también podemos añadir algo de [ASCII Art](http://1lineart.kulaone.com/home2) al inicio de cada línea de tu terminal:

```terminal
prompt_context() {
  local user=`whoami`

  if [[ "$user" != "$DEFAULT_USER" || -n "$SSH_CONNECTION" ]]; then
    prompt_segment $PRIMARY_FG default " %(!.%{%F{yellow}%}.) ¯\_(ツ)_/¯ "
  fi
}
```

#### Instala X-Code Tools
Si no tienes instalado `X-Code` y prefieren no tener que descargarte **4.7GB** instálate las **x-code tools** ejecutando en tu terminal:

```terminal
xcode-select --install
```

#### Instala Sublime Text 3
![Sublime](../img/sublime.png)
---
Sublime es un editor de código ligero y potente. No es gratis pero puedes usarlo sin necesidad de comprarlo.

#### Añade Package Control a Sublime
Para instalar plugins en Sublime Text podemos usar la herramienta package control. Hace que ampliar Sublime sea muy sencillo:
Visita [packagecontrol.io](https://packagecontrol.io/installation)

#### Instala Git + Extras
Git es una herramienta de control de versiones muy potente. Tienes un instalador disponible en la página oficial:
[Git](https://git-scm.com/)

Git Extras nos añade múltiples funcionalidades de gran utilidad:
[Git Extras](https://github.com/tj/git-extras)

Git Open
Abre el repositorio de GitHub desde el terminal.
[Git Open](https://github.com/paulirish/git-open)

#### Instala Node
![NodeJS](../img/nodejs.png)
---
Descarga en instalador de la versión LTE de NodeJS de la web oficial. Además, instalaremos Node Version Manager (NVM) para poder disponer de múltiples versiones de NodeJS instaladas de forma simultanea.

#### NodeJS vía NVM
Para instalar NVM abrimos la terminal y ejecutamos:
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
```

#### Trabajando con NVM
Actualmente la versión de NodeJS más estable es la 4.4.0 Para instalarla con NVM ejecuta:

````
nvm install v4.4.0
````

Si quieres ver todas las versiones de NodeJS que tienes instaladas:

````
nvm list
````

Para utilizar una versión específica:

````
nvm use v4.4.0
````

Para crear un alias:

````
nvm alias default 4
$ default -> 4 (-> v4.4.0)
```


Si necesitas más información sobre NVM visita [su página de GitHub](https://github.com/creationix/nvm).

---

### Actualizando NPM

<img src='../img/Npm-logo.png' width='150' />

NPM es el gestor de paquetes de NodeJS. Para actualizarlo:

```
$ sudo npm install npm -g
```

Comprueba la versión de npm:

```
$ npm --version
```

Actualmente la versión de NPM es la **3.6.0**
