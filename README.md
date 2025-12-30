import pandas as pd

# --- EXTRAÇÃO (Extract) ---
# Criando dados fictícios (simulando seu extrato bancário)
dados = {
    'Item': ['Aluguel', 'Mercado', 'Internet', 'Netflix', 'Academia'],
    'Valor': [1200, 600, 100, 40, 90]
}
salario = 3000
df = pd.DataFrame(dados)

# --- TRANSFORMAÇÃO (Transform) ---
# Calculando o total de gastos e o saldo final
total_gastos = df['Valor'].sum()
saldo_restante = salario - total_gastos

# Adicionando uma coluna de prioridade
df['Prioridade'] = df['Valor'].apply(lambda x: 'Alta' if x > 200 else 'Baixa')

# --- CARREGAMENTO (Load) ---
# Gerando um resumo prático
print("--- RESUMO FINANCEIRO ---")
print(f"Salário: R$ {salario}")
print(f"Total Gasto: R$ {total_gastos}")
print(f"Saldo Livre: R$ {saldo_restante}")
print("\nDetalhamento:")
print(df)

# Salvando em Excel para você abrir no celular/PC
df.to_csv('relatorio_financeiro.csv', index=False)
