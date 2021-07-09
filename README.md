# wordpress-falhas-resolvidas

# 1 - Desativado SSL Cloudfare

Após ativar a função SSL na cloudfare 'Completo (Inrestrito)' o site comecou a apresentar os seguintes erros:

<p align="center">
    <img src="/invalid-ssl-certificate.png" width="800" height="500">
</p>

Resolução:

# 2 - Desativar SSL no phpmyadmin

Necessário acessar o banco de dados do phpmyadmin e na tabela wp_options foi necessário alterar as seguintes linhas abaixo de https:// para http://

siteurl: https://www.seudominio.com.br
home: https://www.seudominio.com.br

para

siteurl: http://www.seudominio.com.br
home: http://www.seudominio.com.br

Após isso conseguimos ter acesso ao site novamente.

# 3 - Corrir erro de acesso ao phpmyamdin com Provedor de Hospedagem

E mesmo desativando o SSL na cloudfare, e o SSL no Servidor do site a mensagens abaixo comecou apresentar erro ao acessar o phpmyadmin:

<p align="center">
    <img src="/cpanel-acesso-phpmyadmin-erro.png" width="900" height="500">
</p>

Resolução: 

Foi necessário entrar em contato com o provedor da hospedagem que realizou a pasta a restauração da pasta /tmp na raiz dessa conta e a mensagem de erro não mais ocorreu.

# 4 - Reinstalado Certificado SSL do Cpanel para manter a segurança do site:

No cpanel em SSL/TLS gerenciar os certificado existe e localizamos o certificao da propria Cpanel e instalamos ele para manter a segurança do site aos visitantes.


# 5 - Reativamos SSL no phpmyadmin 

Necessário acessar o banco de dados do phpmyadmin e na tabela wp_options foi necessário alterar as seguintes linhas abaixo de http:// para https://

siteurl: http://www.seudominio.com.br
home: http://www.seudominio.com.br

para

siteurl: https://www.seudominio.com.br
home: https://www.seudominio.com.br

Após isso conseguimos ter acesso ao site novamente por SSL.

# 6 - Implantar SSL Cloudfare com criptografia entre os 'visitante' ao 'Servidor Cloufare' e 'Servidor Cloufare' ao 'Servidor de Hospedage'. (Pendente)





