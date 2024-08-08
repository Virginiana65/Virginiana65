# Estrutura para armazenar atividades e curtidas
atividades = {
    1: {'usuario': 'usuario1', 'texto': 'Atividade 1', 'curtidas': set()},
    2: {'usuario': 'usuario2', 'texto': 'Atividade 2', 'curtidas': set()},
}

# Função para curtir uma atividade
def curtir_atividade(usuario, id_atividade):
    if id_atividade in atividades:
        atividades[id_atividade]['curtidas'].add(usuario)
        print(f"{usuario} curtiu a atividade {id_atividade}.")
    else:
        print(f"Atividade {id_atividade} não encontrada.")

# Função para visualizar atividades e curtidas
def visualizar_atividades():
    for id_atividade, info in atividades.items():
        curtidas = ', '.join(info['curtidas'])
        print(f"Atividade {id_atividade} (de {info['usuario']}): {info['texto']}")
        print(f"Curtidas: {curtidas if curtidas else 'Nenhuma curtida'}")

# Exemplo de uso
curtir_atividade('usuario1', 1)  # O próprio usuário pode curtir sua atividade
curtir_atividade('usuario2', 1)  # Outro usuário também pode curtir
visualizar_atividades()  # Verificar as atividades e quem curtiu
