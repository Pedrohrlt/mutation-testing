# Mutation Testing Demo

Um projeto educacional demonstrando **testes de mutação** em Python usando a ferramenta **mutmut**.

---

## Sobre o Projeto
Este projeto foi desenvolvido para ensinar os conceitos de **testes de mutação** através de exemplos práticos.  
Testes de mutação avaliam a qualidade de uma suíte de testes introduzindo pequenas alterações (mutações) no código e verificando se os testes conseguem detectá-las.

---

## Estrutura do Projeto
mutation-testing-demo/
├── README.md
├── requirements.txt
├── setup.cfg
├── .gitignore
├── calculator/
│ ├── init.py
│ └── operations.py
└── tests/
├── init.py
└── test_operations.py

yaml
Copy code

---

## Pré-requisitos
- Python 3.8 ou superior
- pip
- Git

---

## Instalação

```bash
git clone https://github.com/Rossi-Luciano/teste_de_software.git
cd teste_de_software/mutation-testing-demo

python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

pip install -r requirements.txt
Como Usar
1. Executar Testes Normais
bash
Copy code
python -m pytest tests/ -v
Saída esperada (resumida):

nginx
Copy code
collected 20 items
20 passed in 0.05s
2. Verificar Cobertura de Código
bash
Copy code
python -m pytest --cov=calculator/ tests/
Saída esperada (resumida):

markdown
Copy code
Name                       Stmts   Miss  Cover
----------------------------------------------
calculator/__init__.py         3      0   100%
calculator/operations.py     101      8    92%
----------------------------------------------
TOTAL                        104      8    92%
✅ Agora a cobertura passou de ~49% para >90%.

3. Executar Testes de Mutação
bash
Copy code
rm -rf .mutmut-cache/
mutmut run
mutmut results
Saída esperada (resumida):

graphql
Copy code
Running mutation testing
⠸ 123/123  🎉 110 🫥 13  ⏰ 0  🤔 0  🙁 0  🔇 0
Resultados
Cobertura de Código: >90%

Taxa de Mutação: >80%

Mutantes Sobreviventes: <15

Exemplos de Testes Adicionados
python
Copy code
def test_subtract(self):
    assert self.calc.subtract(5, 3) == 2
    assert self.calc.subtract(1, 1) == 0

def test_is_even(self):
    assert self.calc.is_even(2) is True
    assert self.calc.is_even(3) is False
Objetivos Educacionais
Mostrar limitações da métrica de cobertura isolada

Demonstrar como o mutation testing encontra lacunas reais

Ensinar processo iterativo de melhoria da qualidade dos testes