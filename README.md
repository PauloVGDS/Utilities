# Utilities
Utilidades que eu provavelmente vou usar  pra resolver algum BO.

# Apagar Usuário Windows
Abre o CMD como administrador.

**Obs: Fique atento para não apagar o único usuário com permissões de Administrador, caso tenha-o feito, formatação obrigatória(eu acho).**

### Comandos:

**net user** - Mostra todos os usuários do computador.

**net user [nome de algum usuário] /active:no** - Desativa um usuário (deixa de aparecer ele como opção).

**net user /delete** - Exclui o usuário permanentemente.

<hr>

# Conversão de método de particionamento de disco

### Microsoft DiskPart versão 10.0.19041.964

**ACTIVE** - Marcar a partição selecionada como ativa.

**ADD** - Adiciona um espelho a um volume simples.

**ASSIGN** - Atribua uma letra de unidade ou um ponto de montagem ao volume selecionado.

**ATTRIBUTES** - Manipular atributos de volume ou disco.

**ATTACH** - Anexa um arquivo de disco virtual.

**AUTOMOUNT** - Habilitar ou desabilitar a montagem automática de volumes básicos.

**BREAK** - Quebrar um conjunto de espelhos.

**CLEAN** - Limpar as informações de configuração ou todas as informações do disco.

**COMPACT** - Tentativas para reduzir o tamanho físico do arquivo.

**CONVERT** - Converter formatos de disco diferentes.

**CREATE** - Criar um volume, partição ou disco virtual.

**DELETE** - Excluir um objeto.

**DETAIL** - Fornecer detalhes sobre um objeto.

**DETACH** - Desanexa um arquivo de disco virtual.

**EXIT** - Sair do DiskPart.

**EXTEND** - Estender um volume.

**EXPAND** - Expande o tamanho máximo disponível em um disco virtual.

**FILESYSTEMS** - Exibir os sistemas de arquivos atuais e com suporte no volume.

**FORMAT** - Formatar o volume ou a partição.

**GPT** - Designar atributos à partição GPT selecionada.

**HELP** - Exibir uma lista de comandos.

**IMPORT** - Importar um grupo de discos.

**INACTIVE** - Marcar a partição selecionada como inativa.

**LIST** - Exibir uma lista de objetos.

**MERGE** - Mescla um disco filho com seus pais.

**ONLINE** - Colocar online um objeto marcado como offline.

**OFFLINE** - Colocar offline um objeto marcado como online.

**RECOVER** - Atualiza o estado de todos os discos do pacote selecionado. Tenta a recuperação em discos do pacote inválido e sincroniza novamente os volumes espelhados e os volumes RAID5 com plex ou dados de paridade obsoletos.

**REM** - Não faz nada. Usado para scripts de comentário.

**REMOVE** - Remover uma atribuição de letra de unidade ou de ponto de montagem.

**REPAIR** - Reparar um volume RAID-5 com um membro danificado.

**RESCAN** - Examinar novamente discos e volumes do computador.

**RETAIN** - Colocar uma partição retida em um volume simples.

**SAN** - Exibir ou definir a política SAN para o sistema operacional inicializado no momento.

**SELECT** - Deslocar o foco para um objeto.

**SETID** - Alterar o tipo de partição.

**SHRINK** - Reduzir o tamanho do volume selecionado.

**UNIQUEID** - Exibe ou define o identificador da GPT (Tabela de Partição GUID) ou a assinatura do MBR (Registro Mestre de Inicialização) de um disco.



# Sequência de comandos para converter uma partição de GPT para MBR (ou o contrário):

**Obs: O passo 4 irá apagar todos os arquivos e configurações da partição selecionada, logo caso necessário faça backup.
Para abrir o CMD no setup de inicialização do Windows uso o atalho `Shift + F10`.**

1. Entra na ferramenta - `diskpart`
2. Lista as partições disponíveis - `list disk`
3. Seleciona a partição desejada - `select disk [número da partição]`
4. Formata a partição já selecionada - `clean`
5. Converter para GPT (pode ser feito o contrário) - `convert gpt`

<hr>

# Ativar/Baixar o Windows/Office por CMD
**Abra o CMD em permissões de administrador**
- Execute o seguinte comando -  `irm https://massgrave.dev/get | iex`
- Selecione as opções para o procedimento desejado.

<hr>

#  Segurança Baseada em Virtualização
1. Verificar Estado
  `Get-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Hypervisor`
2. Ativar
  `bcdedit /set hypervisorlaunchtype auto`
3. Desativar
  `bcdedit /set hypervisorlaunchtype off`

<hr>

# Alterar nome de usuário windows

1. **Win + R**
2. Digitar `netplwiz`
3. Acessar as **Propriedades** do usuário que desejar alterar o nome

<hr>

# Desativar atualizações do Windows

1. **Win + R**
2. Digite `services.msc` e pressione Enter.
3. Localize o serviço chamado "Windows Update".
4. Clique duas vezes sobre ele para abrir as propriedades.
5. No campo "Tipo de inicialização", escolha "Desativado".
6. Clique em "Parar" para interromper o serviço imediatamente.

<hr>

# Comando para baixar qualquer programa
1. Abra o powershell como ADM
2. Execute esse comando `iwr -useb https://christitus.com/win | iex`
3. Escolha as opções para instalar.

