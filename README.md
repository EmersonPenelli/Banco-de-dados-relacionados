# Desenvolvimento

## Instruções do projeto

Desenvolva um banco de dados e relacione tabelas através de chaves estrangeiras ou nomes de colunas iguais. Siga as instruções: crie uma base de dados; crie tabelas nessa base de dados; em cada tabela, adicione atributos; insira dados em cada tabela; utilize os comandos Joins para realizar consultas nas tabelas.

CREATE DATABASE BancoDeDados    <br />
USE BancoDeDados                <br />
CREATE TABLE disciplinas (           <br />
id_disciplina INT AUTO_INCREMENT PRIMARY KEY,       <br />
nome_disciplina VARCHAR(50) NOT NULL,         <br />
nome_professor VARCHAR(50) NOT NULL          <br />
)
CREATE TABLE alunos (             <br />
id_aluno INT AUTO_INCREMENT PRIMARY KEY,         <br />
nome_aluno VARCHAR(50) NOT NULL,          <br />
disciplina_id INT,                       <br />
CONSTRAINT FOREIGN KEY (disciplina_id) REFERENCES disciplinas (id_disciplina)             <br />
)
INSERT INTO disciplinas(nome_disciplina, nome_professor) VALUES ('Banco de dados', 'Maria Alves')         <br />
INSERT INTO disciplinas (nome_disciplina, nome_professor) VALUES ('Python', 'Pietro Souza')     <br />
INSERT INTO disciplinas (nome_disciplina, nome_professor) VALUES ('POO', 'Bia Tavares')      <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Cleiton', 2)          <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Carol', NULL)       <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Ruan', 2)        <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Gabi', 1)            <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Rian', NULL)          <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Mia', 2)            <br />
INSERT INTO alunos (nome_aluno, disciplina_id) VALUES ('Malu', 1)          <br />
SELECT nome_aluno, nome_disciplina from alunos INNER JOIN disciplinas on disciplinas.id_disciplina = alunos.disciplina_id     <br />
SELECT nome_aluno, nome_disciplina from alunos LEFT JOIN disciplinas on disciplinas.id_disciplina = alunos.disciplina_id       <br />
SELECT nome_aluno, nome_disciplina from alunos RIGHT JOIN disciplinas on disciplinas.id_disciplina = alunos.disciplina_id      <br />
SELECT nome_aluno, nome_disciplina from alunos LEFT JOIN disciplinas on disciplinas.id_disciplina = alunos.disciplina_id       
UNION      <br /> 
SELECT nome_aluno, nome_disciplina from alunos RIGHT JOIN disciplinas on disciplinas.id_disciplina = alunos.disciplina_id
