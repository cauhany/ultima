# Uso 

### Passo 1

 - Faça o download do toolkit. Observe que a localização do arquivo mudou do cloudfront, que não será mais atualizado. Deve migrar para a nova versão da biblioteca, e é aconselhado hospedar esse arquivo JS em seu próprio site.
 
 ### Passo 2
 
 - Você pode renomear este arquivo com qualquer descrição que achar adequada, exemplo: string, int... O nome do arquivo baixado deve ser um nome único.
Exemplo: **```toolkitCorporativo.js```**

### Passo 3

 - Coloque o arquivo renomeado em um local acessível publicamente em seu servidor da web.
 - Inclua uma referência ao toolkitCorporativo.js na página cujo perfil você deseja ter:  
                   **```<script type="text/javascript" src="path/to/toolkitCorporativo.js"></script>```**

### Passo 4

- Acione a criação de perfil de maneira simultânea, chamando-a em um script em sua página e incluindo os parâmetros apropriados.

### Passo 5

- Certifique-se de que a função 'ameaçametrix.profile' foi renomeada. Essa função faz parte do download dos clientes toolkitCorporativo ao implementar a ofuscação de tag e deve ser renomeada ou randomizada para não chamar a atenção para o fato de que o ThreatMetrix está sendo usado.

                 <script type="text/javascript">threatmetrix.profile(profiling_domain, org_id, session_id, page_id);</script>
- Substitua profiling_domain, org_id, session_id e, opcionalmente, page_id com os parâmetros apropriados.

### Passo 6


- Observe que você precisará gerar session_id em seu lado do servidor para referenciar a consulta de sessão de seu back end.
- O domínio de criação de perfil será "h.online-metrix.net" se você não configurou esta criação de perfil aprimorada por meio de SSL auto-hospedado.

              <script type="text/javascript">threatmetrix.profile("h.online-metrix.net", "abcd1234", "01f50c4d1430a620a3b50005ffe98541");</script>
    
## Por exemplo:

```<head>
<script type="text/javascript" src="path/to/toolkit.js"/>
<!-- other head content -->
<head>
<body>
<script type="text/javascript">
    var session_id = <%=generateSessionId()%>;
    threatmetrix.profile("<profiling_domain>", "<org_id>", session_id);
</script>
<noscript>
         <iframe style="width: 100px; height: 100px; border: 0; position: absolute; top: -5000px;" src="<profiling doman>/fp/tags?org_id=<org_id>&session_id=<session_id>"></iframe>
</noscript>
</body>
```





















