Configurações básicas para estilização do meu terminal no mac.

###### Última atualização: 21-09-2022

<br>

# Instalando o brew

Instalar o `brew` caso já não esteja instalado.

- https://brew.sh/index_pt-br

```javascript
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

# Instalando Zsh

- https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH

```javascript
brew install zsh
```

Definir `Zsh` como terminal default:

```javascript
chsh - s / usr / local / bin / zsh;
```

# Instalando Oh-My-Zsh

- https://ohmyz.sh/

```javascript
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

# Instalando tema Dracula

- https://draculatheme.com/terminal

Ideal clonar em um local que você vá encontrar depois.

```javascript
git clone https://github.com/dracula/terminal-app.git
```

Configuração:

- `Terminal` > `Preferences`
- Clique na Tab '`Profiles`'
- Clique em '`...`' e em '`Import...`'
- Selecione o arquivo `Dracula.terminal` dentro do repositório que foi baixado
- Agora deve aparecer o `Dracula` como uma opção, selecione ele e coloque como `default`

# Instalando fonte Fira Code

- https://github.com/tonsky/FiraCode

Baixar fonte:

- Baixar a última versão da fonte
- Descompactar e entrar na pasta do repositório
- Entrar na pata `tff`
- Instalar todos (só clicar duas vezes e instalar)

Adicionar no terminal:

- `Terminal` > `Preferences`
- Clique na Tab `Profiles`
- Em `Font` clique em `Change`
- Na coluna `Family` escolha a fonte `Fira Code`

# Instalando tema Space Ship

- https://github.com/spaceship-prompt/spaceship-prompt

```javascript
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
```

```javascript
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Abrir arquivo `~/.zshrc` no terminal

```javascript
nano ~/.zshrc
```

ou

```javascript
vim ~/.zshrc
```

alterar variável `ZSH_THEME` para `spaceship`

```
...

ZSH_THEME="spaceship"

...
```

# Configuração adicional

### Confiurações para melhorar o processamento

Adicionar no fim do arquivo `~/.zshrc`

```
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)
SPACESHIP_USER_SHOW=always
SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "
SPACESHIP_VI_MODE_SHOW=false
```

### Configurações de alguns plugins

```javascript
bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"
```

Abrir o arquivo `~/.zshrc` e abaixo da linha `### End of ZInit's installer chunk`, que foi criada automaticamente, adicionar:

```
...

    ### End of ZInit's installer chunk

    zinit light zdharma/fast-syntax-highlighting
    zinit light zsh-users/zsh-autosuggestions
    zinit light zsh-users/zsh-completions

...
```

Fechar e abrir o terminal para concluir a instalação dos plugins.

### Descrição dos plugins

- `zdharma/fast-syntax-highlighting`: Adiciona syntax highlighting na hora da escrita de comandos que facilita principalmente em reconhecer comandos que foram digitados de forma incorreta.

- `zsh-users/zsh-autosuggestions`: Sugere comandos baseados no histórico de execução conforme você vai digitando.

- `zsh-users/zsh-completions`: Adiciona milhares de completitions para ferramentas comuns como Yarn, Homebrew, NVM, Node, etc, para você precisar apenas apertar TAB para completar comandos.

# Configurar terminal VsCode

Abrir `settings.json`:

- Cmd + Shift + P
- Pesquisar `Open User Settings (JSON)`
- Adicionar no arquivo:

```javascript
"terminal.integrated.defaultProfile.osx": "zsh",
```
