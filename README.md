# Proxy Reverso
Essas configurações vou utilizar para o uso nos sites do Curso de Design.

Esse serviço permite acesso aos seguintes sites:

- Departamento de Design e Moda
- Dashboard
- Associação Amigos do Hospital Regional Universitário de Maringá

Algumas dessas configurações são usadas basicamente como testes e como referência para fazer o site do curso de Design funcionar em um servidor virtual.

Para fazer funcionar, você precisa criar um arquivo **.env**, com as seguintes informações.

```.env
podmansock={sock fornecido pelo podman}
dbUser={usuario do banco de dados}
dbBanco={banco de dados}
dbPassword={senha do banco de dados}
dbRootPassword={senha do root do banco de dados}
pathDDM={local para o site do DDM}
pathCMS={local para o site do CMS}
```

# Acesso ao Dashboard

Para acessar o Dashboard é necessário criar um arquivo de acesso a usuários. No presente trabalho, estamos usando o httpasswd. As informações criadas devem ser armazenadas no arquivo abaixo:

> config/traefik/users.md

Nesse arquivo você deve criar o usuário e senha usando o formato httpasswd, utilize o site abaixo para copiar e colar a sequência no arquivo.

https://hostingcanada.org/htpasswd-generator/

Exemplo de users.md

> admin:$2y$10$wo3YiDj5U4.jKAhekERwwe9gIPqyWkbqRqHAXuVrkmjCCKWhWwA1e
>
> mestre-dos-magos:$2y$10$l63BzYS1A7e9DErx2JzBJ.mqGjnx0OdFP7DqnDY9f2JLFZX9kjfRy



# Como obter o Sock do Podman

Execute o seguinte comando no usuário onde vai funcionar o container.

    systemctl --user enable podman.socket
    systemctl --user start podman.socket
    systemctl --user status podman.socket

O local do sock está conforme indicado na imagem.

![Podman Socket][podman-sock]



[podman-sock]: img/podman-sock.png