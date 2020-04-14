# Composer
Gerenciador de dependências do PHP. Por padrão as bibliotecas são procuradas no [packagist](https://packagist.org/)

## [Instalação](https://getcomposer.org/download/)
* Depois de instalado, para utilizar o composer precisa usar o comndo ``php /path/to/composer.phar``. Para tornar global no Linux, basta mover o ``composer.phar`` para /usr/bin com ``sudo mv /path/to/composer.phar /usr/bin/composer``

## Comandos
``composer [command]``
* Digitando somente ``composer é possível ver todos comandos disponíveis``
* ``--version`` exibe versão do composer
* ``[command] -h`` help sobre [command]
* ``self-update`` atualiza composer
* ``init`` cli para criar composer.json
    * Lembrar de colocar no .gitignore a pasta ``vendor`` e o arquivo ``composer.lock``
* ``init -n`` cria composer.json direto
* ``install`` instala dependências listadas em ``composer.json`` (require e require-dev)
* ``require <vendor>/<name>`` instala dependência no packagist
* ``remove <vendor>/<name>`` remove dependência instalada.
* ``composer du`` e ``composer du -o`` [recarrega namespaces](https://getcomposer.org/doc/03-cli.md#dump-autoload-dumpautoload-)

## Arquivos/Pasta
* ``vendor/`` guarda dependências instaladas (gerado dinâmicamente)
* ``composer.lock`` resolução das dependências (gerado dinâmicamente)
* ``composer.json`` informações sobre o projeto/lib, incluindo scripts e dependências

## Autoload
Adicionar no ``composer.json`` para mapear o namespace da pasta ``src`` o seguinte trecho:
```json
"autoload": {
  "psr-4": {
    "src\\": "src"
  }
}
```
* Sempre que atualizar autoload em ``composer.json`` é necessário executar ``composer dump`` para atualizar o vendor

## Instalar pacotes a partir do github/gitlab etc
Adicionar no ``composer.json`` para especificar as dependências o seguinte trecho:
```json
"repositories": [
  {
    "type": "vcs",
    "url": "git@github.com:user/repo.git"
  }
]
```
* Utilizar ``composer install`` para instalar todas dependências

## Distribuição de pacotes no packagist
É possível conectar repositórios ao packagist gratuitamente para criar biliotecas disponíveis online. A lib é atualizada automaticamente através de hooks do github.

## Observações
* Para utilizar no projeto as dependências, ver arquivo ``app/bootstrap.php``, sugerido pelo professor

