# Trabalho LES

Aplicação desktop Windows (WinForms, .NET Framework 4.6.1) com acesso a banco de dados Firebird.
Cadastros de países, estados, bairros, clientes, departamentos e pedidos, entre outros, com
camada de acesso a dados em `LES_17_I_N/Dao/`.

## Requisitos

- Windows com Visual Studio (suporte a projetos .NET Framework 4.6.1)
- Servidor Firebird rodando em `localhost:3050`
- Pacotes NuGet restaurados (`FirebirdSql.Data.FirebirdClient` 5.8.0, listado em `LES_17_I_N/packages.config`)

## Instalação

1. Clone o repositório: `git clone https://github.com/juninmd/fatec-trabalholes.git`
2. Abra `LES_17_I_N.sln` no Visual Studio.
3. Restaure os pacotes NuGet (o Visual Studio faz isso ao abrir a solução; também via
   `nuget restore LES_17_I_N.sln`).

## Banco de dados

- O arquivo `BANCO.FDB` (Firebird) contém o banco da aplicação. A conexão é montada em
  `LES_17_I_N/Dao/FirebirdRepository.cs` e aponta para `localhost:3050`, usando o diretório de
  dados local com o nome `BANCO.fdb`.
- `query.sql` reúne consultas de referência (por exemplo, listagens de países e estados).

## Uso

1. Compile e execute o projeto `LES_17_I_N` a partir da solução.
2. A aplicação inicia pela tela de login (`frmlogin`, definido em `LES_17_I_N/Program.cs`).

## Estrutura

- `LES_17_I_N/` — código-fonte do projeto WinForms (formulários `frm*.cs`, `Dao/`, `Model/`)
- `LES_17_I_N.sln` — solução do Visual Studio
- `BANCO.FDB` — banco de dados Firebird
- `query.sql` — consultas SQL de referência
- `.github/workflows/` — validação (CI) e release
