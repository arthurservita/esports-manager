# 🎮 E-Sports Manager
### Sistema de Gerenciamento de Torneios de E-Sports

## 👥 Integrantes

- Integrante 1 — Matrícula
- Integrante 2 — Matrícula
- Integrante 3 — Matrícula
- Integrante 4 — Matrícula (opcional)

**Professor:** Jerffeson Gomes Dutra  
**Disciplina:** Programação Orientada a Objetos

## 📌 1. Sobre o projeto

O E-Sports Manager é um sistema desenvolvido para gerenciar torneios e competições de jogos eletrônicos.

A aplicação permite cadastrar jogadores e equipes, criar torneios, gerenciar inscrições, organizar partidas, registrar resultados e acompanhar classificações até a definição do campeão.

O projeto utiliza conceitos de Programação Orientada a Objetos, como encapsulamento, herança, abstração e polimorfismo.

## ⚙️ 2. Funcionalidades

- [ ] Cadastro, consulta, alteração e remoção de jogadores.
- [ ] Cadastro e gerenciamento de equipes.
- [ ] Cadastro de jogos eletrônicos.
- [ ] Criação e gerenciamento de torneios.
- [ ] Inscrição de jogadores e equipes.
- [ ] Validação de requisitos de inscrição.
- [ ] Controle de vagas disponíveis.
- [ ] Encerramento das inscrições.
- [ ] Geração automática de chaves.
- [ ] Organização de partidas e rodadas.
- [ ] Registro e validação de resultados.
- [ ] Avanço automático dos vencedores.
- [ ] Atualização da classificação.
- [ ] Consulta ao histórico de partidas.
- [ ] Identificação do campeão.

## 🧩 3. Modelagem POO

Principais classes previstas:

`Usuario`, `Organizador`, `Competidor`, `Jogador`, `Equipe`, `Jogo`, `Torneio`, `Inscricao`, `FormatoTorneio`, `EliminacaoSimples`, `PontosCorridos`, `Rodada`, `Partida`, `Resultado` e `Classificacao`.

**Polimorfismo:**

1. `Competidor`: especializações em `Jogador` e `Equipe`, com características e regras próprias.
2. `FormatoTorneio`: especializações em `EliminacaoSimples` e `PontosCorridos`, com diferentes métodos de organização e classificação.

## 📋 4. Regras de negócio

1. Um torneio não pode ultrapassar sua capacidade máxima.
2. Um competidor não pode realizar inscrições duplicadas.
3. Somente torneios com inscrições abertas recebem participantes.
4. Equipes devem respeitar os limites de jogadores.
5. Um torneio precisa atingir o mínimo de participantes para começar.
6. Partidas exigem competidores definidos.
7. Somente partidas iniciadas podem receber resultados.
8. Resultados devem respeitar as regras da competição.
9. Apenas usuários autorizados podem alterar resultados.
10. Vencedores avançam conforme o formato do torneio.
11. Competidores eliminados não podem retornar à competição.
12. Torneios finalizados não podem receber novas inscrições.

**Regras identificadas, mas não implementadas:**
- Integração com plataformas externas para obter resultados automaticamente.
- Sistema de ranking individual dos jogadores.
- Sistema de denúncias e contestação de resultados.

## 🔄 5. Estados dinâmicos

**Torneio:** `INSCRICOES_ABERTAS`, `INSCRICOES_ENCERRADAS`, `EM_ANDAMENTO`, `FINALIZADO` e `CANCELADO`.

**Partida:** `AGENDADA`, `EM_ANDAMENTO`, `FINALIZADA` e `CANCELADA`.

As transições entre estados deverão respeitar as regras da aplicação.

## 🔐 6. Autenticação e autorização

O sistema terá dois perfis:

- **Organizador:** administra torneios, inscrições, partidas e resultados.
- **Competidor:** realiza inscrições e consulta torneios, partidas e classificações.

## ⚠️ 7. Exceções personalizadas

- `TorneioLotadoException`
- `CompetidorJaInscritoException`
- `InscricaoEncerradaException`
- `ElencoInvalidoException`
- `ResultadoInvalidoException`
- `TransicaoEstadoInvalidaException`
- `OperacaoNaoAutorizadaException`

## 🚨 8. Situações de risco

**1. Inscrições simultâneas na última vaga**

- Situação: dois competidores tentam ocupar a última vaga.
- Problema: ambas as operações identificam a vaga como disponível.
- Impacto: excesso de participantes.
- Mitigação: validar disponibilidade e registrar a inscrição como uma operação atômica.
- Classes: `Torneio` e `Inscricao`.

**2. Inscrição duplicada**

- Situação: um competidor tenta se inscrever novamente.
- Problema: ausência de verificação de inscrições anteriores.
- Impacto: duplicidade nas chaves.
- Mitigação: validar inscrições existentes.
- Classes: `Competidor`, `Inscricao` e `Torneio`.

**3. Alteração de equipe durante o campeonato**

- Situação: jogadores são removidos ou adicionados após o início.
- Problema: alteração da composição original.
- Impacto: inconsistência nos registros competitivos.
- Mitigação: bloquear alterações após o início do torneio.
- Classes: `Equipe`, `Jogador` e `Torneio`.

**4. Resultado incorreto**

- Situação: organizador registra um vencedor errado.
- Problema: classificação já atualizada com informação incorreta.
- Impacto: avanço indevido de competidores.
- Mitigação: permitir correção controlada e atualização das rodadas afetadas.
- Classes: `Resultado`, `Partida` e `Classificacao`.

**5. Ausência de competidor**

- Situação: jogador ou equipe não comparece à partida.
- Problema: confronto permanece sem resultado.
- Impacto: atraso na competição.
- Mitigação: permitir registro de vitória por ausência (WO), conforme o regulamento.
- Classes: `Partida`, `Resultado` e `Torneio`.

## 💾 9. Persistência de dados

As informações serão armazenadas em arquivos e carregadas automaticamente ao iniciar a aplicação, preservando os dados entre execuções.

## 📊 10. Diagrama UML

O diagrama apresentará as classes, atributos, métodos, relações de herança, associações e multiplicidades.

![Diagrama de Classes UML](CAMINHO_DO_DIAGRAMA)

## 🛠️ 11. Tecnologias

- Linguagem: [Preencher]
- Paradigma: Programação Orientada a Objetos.
- Persistência: Arquivos.
- Controle de versão: Git e GitHub.
- Modelagem: UML.

## ▶️ 12. Como executar

**Pré-requisitos:** [Informar versão e ferramentas necessárias.]

Clonar o repositório:

```bash
git clone URL_DO_REPOSITORIO
cd NOME_DO_REPOSITORIO
```

Executar a aplicação:

```bash
# Inserir o comando de execução do projeto.
```

## 📦 13. Código-fonte

[Link para baixar o projeto compactado (.zip)]

## 📌 14. Considerações finais

O E-Sports Manager busca demonstrar a aplicação dos conceitos de Programação Orientada a Objetos em um sistema de gerenciamento de competições de jogos eletrônicos, utilizando regras de negócio, polimorfismo, persistência de dados e controle de estados.
