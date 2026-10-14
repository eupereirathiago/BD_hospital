# Documentação — hospital_aula2

## 1. Introdução
Este projeto apresenta um banco de dados hospitalar para organizar informações de pacientes, médicos, consultas, exames e medicamentos.

## 2. Entidades e atributos

### Pacientes
| Campo | Tipo | Descrição |
|---|---|---|
| id_paciente | INT | Chave primária e identificador único |
| nome | VARCHAR(100) | Nome completo |
| cpf | VARCHAR(14) | CPF, único quando informado |
| data_nascimento | DATE | Data de nascimento |
| telefone | VARCHAR(20) | Telefone para contato |
| endereco | VARCHAR(150) | Endereço |

### Médicos
| Campo | Tipo | Descrição |
|---|---|---|
| id_medico | INT | Chave primária |
| nome | VARCHAR(100) | Nome completo |
| crm | VARCHAR(20) | Registro profissional, único |
| especialidade | VARCHAR(80) | Especialidade médica |
| telefone | VARCHAR(20) | Telefone para contato |

### Consultas
| Campo | Tipo | Descrição |
|---|---|---|
| id_consulta | INT | Chave primária |
| id_paciente | INT | Chave estrangeira para pacientes |
| id_medico | INT | Chave estrangeira para médicos |
| data_hora | DATETIME | Data e hora da consulta |
| motivo | VARCHAR(200) | Motivo do atendimento |
| status | VARCHAR(20) | Situação da consulta |

### Exames
| Campo | Tipo | Descrição |
|---|---|---|
| id_exame | INT | Chave primária |
| id_paciente | INT | Chave estrangeira para pacientes |
| id_medico | INT | Chave estrangeira para médicos |
| nome_exame | VARCHAR(100) | Nome do exame |
| data_exame | DATE | Data do exame |
| resultado | TEXT | Resultado do exame |

### Medicamentos
| Campo | Tipo | Descrição |
|---|---|---|
| id_medicamento | INT | Chave primária |
| nome | VARCHAR(100) | Nome do medicamento |
| fabricante | VARCHAR(100) | Fabricante |
| dosagem | VARCHAR(50) | Dosagem |
| quantidade_estoque | INT | Quantidade disponível em estoque |

## 3. Relacionamentos
- Um paciente pode ter várias consultas; cada consulta está ligada a um paciente.
- Um médico pode realizar várias consultas; cada consulta está ligada a um médico.
- Um paciente pode ter vários exames; cada exame está ligado a um paciente.
- Um médico pode solicitar vários exames; cada exame está ligado ao médico solicitante.
- A tabela medicamentos mantém o cadastro e o controle básico do estoque.

## 4. Conclusão
A estrutura permite organizar as principais informações hospitalares em tabelas relacionadas. As chaves primárias identificam os registros, enquanto as chaves estrangeiras estabelecem relacionamentos entre as entidades.
