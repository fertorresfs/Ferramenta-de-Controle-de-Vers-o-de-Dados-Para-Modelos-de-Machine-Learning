# Ferramenta-de-Controle-de-Vers-o-de-Dados-Para-Modelos-de-Machine-Learning

## Como usar:

* Criar o banco de dados: O código cria automaticamente o banco de dados data_versioning.db se ele não existir.
* Versionar: versionar_dados("caminho/para/seu/arquivo.csv", "Descrição da versão")
* Carregar: df = carregar_versao("hash_da_versão")

## Explicação:

* gerar_hash: Gera um hash SHA-256 para o arquivo.
* versionar_dados:
** Gera o hash do arquivo.
** Verifica se o hash já existe no banco de dados.
** Copia o arquivo para o diretório data_versions.
** Salva os metadados (hash, caminho do arquivo, timestamp, descrição) no banco de dados.
* carregar_versao:
** Busca o caminho do arquivo no banco de dados com base no hash.
** Carrega o arquivo CSV usando pandas.

## Limitações e próximos passos:

* Armazenamento local: Os dados são armazenados localmente. Para um sistema mais robusto, considere usar armazenamento em nuvem.
* Apenas CSV: O código funciona apenas com arquivos CSV. Adapte-o para suportar outros formatos de dados.
* Tratamento de erros: Adicione tratamento de erros mais robusto.
* Interface de linha de comando: Crie uma CLI para facilitar o uso.
* Integração com Git: Considere integrar com Git para versionar os metadados.
* Diferenças entre versões: Implemente uma função para comparar diferentes versões dos dados.
