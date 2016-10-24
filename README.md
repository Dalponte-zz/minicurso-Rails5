# minicurso-Rails5
Projeto que será desenvolvido no minicurso de Rails 5 em 25/10/2016 no Tecsul

<h3>Vagrant Box Setup</h3>
Para manter todos os participantes no mesmo escopo, uma máquina virtual em Vagrant será utilizada para rodar o Rails 5.
O Vagrant e um software que permite gerenciar VMs que rodam com o VirtualBox, configurando-as por meio de um arquivo onde é possível importar VMs já preparadas, reseta-las e tudo mais sem ser necessário configura-las do zero.

Portanto, alguns programas são necessários:
- VirtualBox
 - https://www.virtualbox.org/
- Vagrant
 - https://www.vagrantup.com/downloads.html
- Qualquer bash (utilizado para trabalhar com o rails e vagrant via comandos no terminal)
 - https://git-for-windows.github.io/
- VM préconfigurada:
 - https://github.com/lcreid/rails-5-jade
- IDE ou editor a escolha:
 - https://www.sublimetext.com/ (editor de texto gratuíto);
 - https://www.jetbrains.com/ruby/ (IDE paga, mas é possível obte-lo com "free trial" de 30 dias, ou com e-mail de alunos da UTFPR é possível conseguir a licença de estudante);
 - https://dzone.com/articles/5-ides-ruby-rails-developers (Outras opções);
 
<h3>Criando o projeto Rails 5 com a VM</h3>
- Instalar Virtual box, Vagrant e Bash;
- Iniciar o Bash, acessando uma pasta a escolha. Recomendado uma pasta de fácil acesso, como `C:/minicurso_rails5` em windows ou `/home/[usuário]/minicurso_rails5`
- Obter os arquivos da VM com o comando no terminal (estando na pasta criada acima): `vagrant init jadesystems/rails5` ;
- Ordenar ao Vagrant para criar (baixar) a maquina virtual e inicia-la: `vagrant up` ;
- Acessar o terminal da máquina virtual via SSH (como se fosse acesso remoto a outra máquina): `vagrant ssh`;
- Adentrar à pasta compartilhada pelo vagrant da VM com a sua maquina (mais detalhes em *Obersevações*): `cd /vagrant`;
- Criar um projeto Rails: `rails new .`

Pronto. Agora, se você acessar a pasta escolhida (A criada acima `minicurso_rails5`) você verá que os arquivos do framework.

- Edite o arquivo `config/environments/development.rb` (usando sua IDE/editor) substituíndo (ou comentando) a última linha:

`# config.file_watcher = ActiveSupport::EventedFileUpdateChecker` deletar ou comentar(colocando # no início)
`config.file_watcher = ActiveSupport::FileUpdateChecker ` Esta fica no lugar

Para sair da VM no terminal, pressione Ctrl+D ou o comando `exit`. A VM continuará rodando, para desliga-la, utilize o comando `vagrant halt`. Para incia-la novamente, utilize o comando `vagrant up` (sempre estando na pasta da VM).

<h3>Observações</h3>
- O vagrant "liga" a pasta criada para instalar o projeto rails ao diretório `/vagrant` na VM, assim, você pode editar os códigos fonte utilizando qualquer SO, mas rodando o Ruby em um ambiente linux. Vale a pena ver: https://friendsofvagrant.github.io/v1/docs/getting-started/why.html
- PODE ser necessário ativar a virtualização no setup da placa mãe de sua máquina. Assim, segue alguns links que encontrei para ajudar a resolução de possíveis problemas:
No geral, basta procurar no google as palavras chave "ativar virtualização + [marca do notebook ou placa mãe]".
 - https://www.youtube.com/watch?v=886cH0E-T7I
 - http://www.howtogeek.com/213795/how-to-enable-intel-vt-x-in-your-computers-bios-or-uefi-firmware/
 - http://www.sysprobs.com/disable-enable-virtualization-technology-bios
