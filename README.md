# Projeto-Final-M3

**PROJETO FINAL M3**

Para este projeto final M3, a squad 2 decidiu utilizar a ideia de um mini projeto de um integrante do grupo, a ideia no caso foi criar um aplicativo que conecta pessoas a profissionais de diversos serviços.

**DIAGRAMA CONCEITUAL**

O diagrama conceitual que foi feito no dbdiagram.io, possui duas entidades principais: o usuário e o prestador de serviço. Essas duas entidades têm uma relação entre si de muitos para muitos, onde um usuário pode solicitar vários serviços, assim como o prestador de serviços pode prestar vários serviços.
Cada entidade principal tem relação com outras entidades de um para um ou de um para muitos.

![site_servicos](https://github.com/deboratobalo/Projeto-Final-M3/assets/116042338/f8527c20-0779-4e42-a4d4-2dfe3018a74e)


**CONSULTAS DO BANCO DE DADOS**

**Conta o numero de profissionais por categoria**
```
select categorias.nome_categoria, count(profissionais.id_profissional) as total_profissionais
from tb_profissionais as profissionais
inner join tb_categorias as categorias on profissionais.categoria_id = categorias.id_categoria
group by categorias.nome_categoria;
```

**Conta o numero de usuarios por estados** 
```
select estados.estado, count(usuarios.id_usuario) as total_usuarios
from tb_enderecos as estados
inner join tb_usuarios as usuarios on estados.id_usuario = usuarios.id_usuario
group by estados.estado;
```

**Conta o numero de profissionais por estado** 
```
select estados.estado, count(profissionais.id_profissional) as total_profissionais
from tb_enderecos as estados
inner join tb_profissionais as profissionais on estados.id_profissional = profissionais.id_profissional
group by estados.estado;
```


**Mostra quantidade de mensagens por profissionais**
```
SELECT tb_profissionais.nome, tb_profissionais.sobrenome,
       COUNT(tb_Mensagem.id_mensagem) AS qtd_mensagens
FROM tb_profissionais
LEFT JOIN tb_Mensagem ON tb_profissionais.id_profissional = tb_Mensagem.profissional_id
GROUP BY tb_profissionais.nome;
```

**Conta o número de mensagens por usuarios**
```
SELECT tb_usuarios.nome, tb_usuarios.sobrenome,
       COUNT(tb_Mensagem.id_mensagem) AS qtd_mensagens
FROM tb_usuarios
LEFT JOIN tb_Mensagem ON tb_usuarios.id_usuario = tb_Mensagem.usuario_id
GROUP BY tb_usuarios.nome;
```



**GRÁFICOS**

![Usuarios_por_Estado](https://github.com/deboratobalo/Projeto-Final-M3/assets/116042338/e1c3e925-d230-429c-b3f8-3b0a1f2ed8db)

![Profissionais_por_Estado](https://github.com/deboratobalo/Projeto-Final-M3/assets/116042338/7828c174-1867-442e-a651-03c062b27563)

![Profissionais_por_Categoria](https://github.com/deboratobalo/Projeto-Final-M3/assets/116042338/1896621c-0a98-44b1-a8eb-08cdf8ae290c)


Link Apresentação

Para acessar o link da apresentação é só seguir o link abaixo

 [Apresentação](https://www.canva.com/design/DAF0kI1xCEI/FVb0SClSORHMmLhaLncleg/edit?utm_content=DAF0kI1xCEI&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
