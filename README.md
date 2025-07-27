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

# Sequência de comandos para converter uma partição de GPT para MBR(ou o contrário) usando diskpart:

**Obs: O passo 4 irá apagar todos os arquivos e configurações da partição selecionada, logo caso necessário faça backup.
Para abrir o CMD no setup de inicialização do Windows uso o atalho `Shift + F10`.**

1. Entra na ferramenta - `diskpart`
2. Lista as partições disponíveis - `list disk`
3. Seleciona o disco desejado - `select disk [número da partição]`
4. Formata o disco selecionado - `clean`
5. Converter para GPT/MBR - `convert gpt` ou `convert mbr`

<hr>

# Sequência de comandos para formatar uma unidade de armazenamento usando diskpart

1. Entra na ferramenta - `diskpart`
2. Lista as partições disponíveis - `list disk`
3. Seleciona o disco desejado - `select disk [número da partição]`
4. Formata o disco selecionado- `clean`
5. Cria uma partição primária - `create partition primary`
6. Formata a partição para FAT32 - `format fs=fat32 quick`
7. Atribuição de uma letra a partição(X == qualquer letra) - `assign letter=X`

<hr>

# Ativar/Baixar o Windows/Office por CMD
**Abra o CMD em permissões de administrador**
- Execute o seguinte comando -  `irm https://get.activated.win | iex`
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

<hr>

# Adaptadores de rede do Windows
1. **Win + R**
2. Digite `ncpa.cpl` ou `control netconnections`
