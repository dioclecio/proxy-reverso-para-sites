# Proxy Reverso
Essas configurações vou utilizar para o uso nos sites do Curso de Design.

Algumas dessas configurações são usadas basicamente como testes e como referência para fazer o site do curso de Design funcionar em um servidor virtual.

Para fazer funcionar, você precisa criar um arquivo **.env**, com as seguintes informações.

    podmansock={sock fornecido pelo podman}
    dbUser={usuario do banco de dados}
    dbBanco={banco de dados}
    dbPassword={senha do banco de dados}
    dbRootPassword={senha do root do banco de dados}
    pathDDM={local para o site do DDM}
    pathCMS={local para o site do CMS}

# Como obter o Sock do Podman
Execute o seguinte comando no usuário onde vai funcionar o container.

    systemctl --user enable podman.socket
    systemctl --user start podman.socket
    systemctl --user status podman.socket

O local do sock está conforme indicado na imagem.

![Podman Socket][podman-sock]



[podman-sock]: img/podman-sock.png