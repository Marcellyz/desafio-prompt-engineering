# Questão 4 – Endpoint com FastAPI e Validação de Objeto

## Pergunta

Utilizando uma ferramenta de IA generativa, crie um endpoint com FastAPI que valide e processe a entrada de um objeto do tipo `Item`. Siga as especificações abaixo:

- `nome`: string com máximo de 25 caracteres
- `valor`: float
- `data`: tipo date, não pode ser maior que a data atual

O endpoint deve retornar o objeto com um novo campo `uuid` gerado dinamicamente.

---

## Técnica Utilizada

**CIDI (Contexto, Instrução, Detalhamento, Input)**

## IA Utilizada
  <img align="inline_block" alt="chat gpt" src="https://img.shields.io/badge/chatGPT-74aa9c?style=for-the-badge&logo=openai&logoColor=white"/>

## Prompt

**Context:**  
Você é um desenvolvedor backend experiente, especializado em criação de APIs com FastAPI e validações com Pydantic. Precisa criar um endpoint que receba e valide um objeto do tipo `Item`, seguindo regras específicas.

**Instruction:**  
Crie um endpoint POST em FastAPI que receba um JSON do tipo `Item`, valide os dados recebidos de acordo com os critérios abaixo e adicione dinamicamente um campo `uuid` ao retorno.

**Details:**  
O objeto `Item` deve conter:
- `nome`: string com máximo de 25 caracteres.
- `valor`: número decimal (`float`).
- `data`: tipo `date`, não pode ser uma data futura.  
Após validação, o endpoint deve retornar o mesmo objeto com um campo adicional `uuid`, gerado com `uuid4`.

**Input:**  
Crie o código completo em FastAPI, incluindo importações necessárias e validações com Pydantic.

---

## Código Gerado

```python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel, Field, validator
from uuid import uuid4
from datetime import date
from typing import Optional

app = FastAPI()

class Item(BaseModel):
    nome: str = Field(..., max_length=25)
    valor: float
    data: date

    @validator('data')
    def validar_data(cls, v):
        if v > date.today():
            raise ValueError("A data não pode ser futura.")
        return v

class ItemComUUID(Item):
    uuid: str

@app.post("/item", response_model=ItemComUUID)
def criar_item(item: Item):
    item_com_uuid = ItemComUUID(**item.dict(), uuid=str(uuid4()))
    return item_com_uuid

```