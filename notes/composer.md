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
* ``install`` instala dependências listadas em ``composer.json`` (require e require-dev)
* ``require <vendor>/<name>`` instala dependência no packagist
* ``remove <vendor>/<name>`` remove dependência instalada.

## Arquivos/Pasta
* ``vendor/`` guarda dependências instaladas (gerado dinâmicamente)
* ``composer.lock`` resolução das dependências (gerado dinâmicamente)
* ``composer.json`` informações sobre o projeto/lib, incluindo scripts e dependências

## Observações
* Para utilizar no projeto as dependências, ver arquivo ``bootstrap.php``, sugerido pelo professor

