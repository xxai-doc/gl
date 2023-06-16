<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Parte do código do sitio web é de código aberto, benvido para axudar a optimizar a tradución.

## código front-end

* [código front-end](https://github.com/xxai-art/web)
* [Paquetes de idiomas para o sitio no seu conxunto](https://github.com/xxai-art/web/tree/main/i18n)
* [Paquetes de idiomas para módulos de inicio de sesión](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Web Documentación multilingüe](https://github.com/xxai-doc)

A linguaxe de programación front-end é [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , que engade algunhas funcións baseadas na sintaxe coffeescript, consulte [./coffee_plus.md](./coffee_plus.md) .

## Internacionalización de sitios web e documentos

Constrúe nos seguintes 3 proxectos

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  O sufixo é `.mdt` , podes usar a sintaxe similar a `<+ ./coffee_plus/import.js>` para facer referencia a ficheiros externos e xerar rebaixa co sufixo `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  A tradución de Markdown non traducirá códigos e ligazóns e almacenará en caché as frases traducidas. Se se modifica a tradución pero non se modifica o texto orixinal, executala de novo non sobrescribirá a modificación da tradución.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Ficheiros de idiomas para traducir sitios web xerados por `yaml` .
