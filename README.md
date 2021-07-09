# wordpress-falhas-resolvidas

# 1 - Desativado SSL Cloudflare

Após ativar a função SSL na cloudflare 'Completo (Inrestrito)' o site comecou a apresentar os seguintes erros:

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

# 3 - Corrir erro de acesso ao phpmyadmin com Provedor de Hospedagem

E mesmo desativando o SSL na cloudflare, e o SSL no Servidor do site a mensagens abaixo comecou apresentar erro ao acessar o phpmyadmin:

<p align="center">
    <img src="/cpanel-acesso-phpmyadmin-erro.png" width="1500" height="500">
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

home: https://www.seudominio.com.brt

Após isso conseguimos ter acesso ao site novamente por SSL.

# 7 - 404 No found

Após tentativa de acesso a painel de administração do WordPress apresentou a seguinte falha:

<p align="center">
    <img src="/404-not-found.png" width="800" height="500">
</p>

Resolução:

Foi necessário restaurar as configurações originais do arquivo .htaccess assim o acesso foi permitido ao wordpress.

# 6 - SSL Cloudflare com criptografia:

Implantar  entre os 'visitante' ao 'Servidor Cloudflare' e 'Servidor Cloudflare' ao 'Servidor de Hospedagem'. (Pendente)

# SSL/TLS

Completo (Ativar)

* Sempre use o modo completo para uso em loja virtual.

* NOTA: Se sua loja estiver configurado com o modo 'flexivel' ou 'completo(estrito)' sua loja não vai funcionar bem, pode dar erro no carrinho ou em outras configurações. 

# Page Rules

Crie uma Page Rule para alvesnet.com.br


Se o URL corresponder: Usando o caractere asterisco (*), você pode criar padrões dinâmicos que podem corresponder a muitas URLs, em vez de apenas uma. Todos os URLs não diferenciam maiúsculas de minúsculas. Leia mais

exemplo: seudomninio.com.br/*

Em seguida, as configurações são:

URL de encaminhamento: 301 - Redirecionamento permanente

Digite um destino URL: https://www.seudominio.com.br

Não é possível adicionar configurações adicionais com "URL de encaminhamento" selecionado.

# Scrape Shield

Proteja o conteúdo do seu site

Obfuscação de Endereço de Email - (Desativar)
* Desativar essa opção pois se não ela vai ficar toda hora enviando e-mail para você.

*Exiba endereços de email ofuscados em seu site para evitar a colheita por bots e spammers, sem alterações visíveis no endereço para visitantes humanos.

Exclusões do Lado do Servidor - (Ativado)

* Ocultar automaticamente conteúdo específico de visitantes questionáveis.

Proteção de Hotlink - (Desativado)

* Proteja suas imagens de links fora do site.

