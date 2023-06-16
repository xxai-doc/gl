<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Recoméndase instalar primeiro nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , e despois `direnv allow` despois de entrar no directorio ( [o .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) executarase automaticamente despois de entrar no directorio).

O significado é: tradución do chinés ao xaponés, coreano, inglés, tradución do inglés a todas as outras linguas. Se só queres admitir chinés e inglés, podes escribir `zh: en` .

O significado é: tradución do chinés ao xaponés, coreano, inglés, tradución do inglés a todas as outras linguas. Se só queres admitir chinés e inglés, podes escribir `zh: en` .

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

### Instrucións de automatización de tradución de documentos

Consulte o repositorio de código [xxai-art/doc](https://github.com/xxai-art/doc)

Recoméndase instalar primeiro nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , e despois `direnv allow` despois de entrar no directorio ( [o .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) executarase automaticamente despois de entrar no directorio).

Para evitar a gran base de código traducida a centos de idiomas, creei unha base de código separada para cada idioma e creei unha organización para almacenar a base de código.

Establecer a variable de ambiente `GITHUB_ACCESS_TOKEN` e executar [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) crearase automaticamente o repositorio de código.

Por suposto, tamén podes poñelo nunha base de código.

Referencia do script de tradución [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

O código do script interprétase do seguinte xeito:

[bunx](https://bun.sh/docs/cli/bunx) é un substituto de npx, que é máis rápido. Por suposto, se non tes bun instalado, podes usar `npx` no seu lugar.

`bunx mdt zh` representa `.mdt` no directorio zh como `.md` , consulta os dous ficheiros ligados a continuación

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` é o código principal para a tradución (se só tes `nodejs` instalado, pero `bun` e `direnv` non están instalados, tamén podes executar `npx i18n` para traducir).

Analizará [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , a configuración de `i18n.yml` neste documento é a seguinte:

```
en:
zh: ja ko en
```

O significado é: tradución do chinés ao xaponés, coreano, inglés, tradución do inglés a todas as outras linguas. Se só queres admitir chinés e inglés, podes escribir `zh: en` .

O último é [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , que extrae o contido entre o título principal e o primeiro subtítulo do `README.md` de cada idioma para xerar unha entrada `README.md` . O código é moi sinxelo, podes miralo ti mesmo.

A API de Google úsase para a tradución gratuíta. Se non podes acceder a Google, configura e establece un proxy, como:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

O script de tradución xerará unha caché traducida no directorio `.i18n` , comprobeo co `git status` e engádeo ao repositorio de código para evitar traducións repetidas.

Executa `bunx i18n` cada vez que modifiques a tradución para actualizar a caché.

Se o texto orixinal e a tradución se modifican ao mesmo tempo, a caché confundirase, polo que se quere modificala, só pode modificar unha e, a continuación, executa `bunx i18n` para actualizar a caché.
