# Coleta de dados da API Web do Spotify

## Sobre

A API Web do Spotify permite a criação de aplicativos que podem interagir com o serviço de streaming do Spotify, fornecendo as seguintes atividades:

- Recuperação de metadados de conteúdo
- Captura de recomendações
- Criação e gerenciamento de playlists
- Controle da reprodução

O objetivo deste projeto é realizar a comunicação com a API, coletar 100 tuplas do Spotify e armazenar os dados no banco de dados PostgreSQL (>=12). Para atingir este objetivo, é necessário (i) realizar o diagrama entidade relacionamento e mapeamento relacional dos 12 endpoints existentes na documentação. Em seguida, (ii) o código da aplicação deverá solicitar da API 100 tuplas de pelo menos uma das endpoints.

## Entregas

- [Diagrama Entidade Relacionamento | PDF]()
- [DUMP do Banco de Dados | dump.sql]()
- [Código de Coleta | load_spotify.sql]()
- [Apresentação da Aplicação | 10 min | Restrito]()

## Links e Referências

- [Descrição do trabalho de Laboratório de Banco de Dados | PDF](TR___TRABALHO_PRÁTICO_LBD_2024.pdf)
- [Documentação da API Web | Spotify Developer](https://developer.spotify.com/documentation/web-api)