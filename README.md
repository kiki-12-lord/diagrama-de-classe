# diagrama-de-classe

```python
from datetime import datetime, date

class Pessoa:
    def __init__(self, codigo, nome, data_nascimento):
        self.codigo = codigo
        self.nome = nome
        # data_nascimento deve ser passada no formato 'AAAA-MM-DD'
        self.data_nascimento = datetime.strptime(data_nascimento, '%Y-%m-%d').date()

    def idade(self):
        hoje = date.today()
        idade = hoje.year - self.data_nascimento.year
        # Ajuste se ainda não fez aniversário este ano
        if (hoje.month, hoje.day) < (self.data_nascimento.month, self.data_nascimento.day):
            idade -= 1
        return idade

    def __str__(self):
        return f'{self.nome} (Código: {self.codigo}) - Idade: {self.idade()} anos'

# Exemplo de uso:
p = Pessoa(1, "João da Silva", "1990-05-13")
print(p)


```
