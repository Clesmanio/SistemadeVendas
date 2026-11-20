# Sistema de Vendas

Aplicação web em Django para cadastrar clientes e produtos e consultar vendas registradas em SQLite. A página inicial reúne totais de clientes, produtos e vendas, além das vendas mais recentes. O Django Admin permite gerenciar os registros.

## Modelo de dados

Uma venda pertence a um cliente. A tabela intermediária `ItemVenda` liga a venda aos produtos e guarda a quantidade e o valor unitário de cada item. Os modelos estão em [vendas/models.py](./vendas/models.py).

## Execução local

```sh
git clone https://github.com/Clesmanio/SistemadeVendas.git
cd SistemadeVendas
python -m venv .venv
```

Ative o ambiente com `.\.venv\Scripts\Activate.ps1` no PowerShell ou com `source .venv/bin/activate` no Linux e no macOS. Use uma versão de Python compatível com o Django 3.x indicado no [requirements.txt](./requirements.txt).

```sh
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Abra a [página inicial](http://127.0.0.1:8000/) ou o [painel administrativo](http://127.0.0.1:8000/admin/). O repositório inclui um banco SQLite de exemplo. Se estiver usando um banco novo, você pode carregar a fixture com `python manage.py loaddata vendas/fixtures/dados_teste.json`.

## Estrutura

- [vendas/](./vendas/) reúne modelos, formulários, telas e dados de teste.
- [vendas_project/](./vendas_project/) contém as configurações e as rotas do projeto.
