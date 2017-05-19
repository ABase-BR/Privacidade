# EncFS - an Encrypted Filesystem

O EncFS fornece um sistema de arquivos criptografado no espaço do usuário. Ele é executado em userspace, usando a biblioteca FUSE para a interface do sistema de arquivos. EncFS é um software de código aberto, licenciado pela LGPL.

EncFS tem agora mais de 10 anos de idade (primeiro lançamento em 2003). Foi escrito porque o NFS antigo e os sistemas de arquivos criptografados baseados no kernel, como o CFS, não acompanharam o desenvolvimento do Linux. Quando FUSE se tornou disponível, eu escrevi uma substituição CFS para meu próprio uso e lançou a primeira versão para Open Source em 2003.

O EncFS criptografa arquivos individuais, traduzindo todas as solicitações para o sistema de arquivos EncFS virtual nas operações criptografadas equivalentes no sistema de arquivos brutos.

Site do projeto   : https://vgough.github.io/encfs/

Projeto no github : https://github.com/vgough/encfs


## Instalando no Debian

```sh
sudo apt-get install encfs
```

## Criando diretório
Podemos criar um diretório criptografado em um local onde os arquivos ficaram visíveis.

```sh
encfs ~/.greenmind ~/greenmind
```

Vai ser pedido uma senha , digite a senha de sua escolha.

Podemos notar que foi criado um novo ponto de montagem com o nome do nosso diretório no sistema de arquivos.


## Usando diretório e criptografando.
Podemos fazer qualquer ação nesse diretório , e todo os arquivos criptografados ficaram em **~/.greenmind**.

Ao terminar a ação em nosso diretório vamos criptografar os arquivos.

**Criptografando**
```sh
fusermount -u ~/greenmind
```

Nossos arquivos foram criptografados com segurança e podemos ver que o diretório foi desmontado.

Mais e agora para usar novamente ? Podemos usar o comando
**descriptografando**
```sh
encfs ~/.greenmind ~/greenmind
```

Podemos ver que vai ser montado novamente o diretório.
