## Sesión 2 - Configura y personaliza tu entorno

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
En lugar de hacerlo mediante el instalador de NodeJS de la web oficial, lo haremos con Node Version Manager (NVM) para poder disponer de múltiples versiones de NodeJS instaladas de forma simultanea.
![NVM](https://github.com/creationix/nvm)

#### NodeJS vía NVM
Para instalar NVM abrimos la terminal y ejecutamos:
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
```

#### Trabajando con NVM

Para listar todas las versiones disponibles:

```
nvm ls-remote
```


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
