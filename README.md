# Atividade de Redes de Computadores — Cisco Packet Tracer

## 1. Identificação

| Campo | Informação |
|---|---|
| **Disciplina** | Redes de Computadores |
| **Curso** | CST em Redes de Computadores |
| **Instituição** | Instituto Federal de Rondônia — IFRO |
| **Aluno** | Gabriel Mota Barroso |
| **Ferramenta utilizada** | Cisco Packet Tracer |

---

## 2. Objetivo da atividade

Esta atividade consiste na construção de uma simulação de ambiente hierárquico de rede local utilizando o Cisco Packet Tracer, praticando os conceitos de rede hierárquica e comutação em redes locais (padrões 802.3).

A topologia foi organizada respeitando as três camadas do modelo hierárquico:

- Núcleo (Core)
- Distribuição
- Borda

Foram utilizadas conexões FastEthernet, GigabitEthernet e fibra óptica, além de ligações físicas preparadas para futuras agregações de link (link aggregation), conforme especificado na atividade.

---

## 3. Topologia da rede

A rede foi organizada conforme o modelo hierárquico, representado na imagem abaixo:

<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/06202e33-3838-4470-b7e7-9cea507ac98c"/>

---

## 4. Equipamentos utilizados

| Equipamento | Quantidade |
|---|---|
| Roteador | 1 |
| Switches de núcleo | 2 |
| Switches de distribuição | 2 |
| Switches de borda | 4 |
| Computadores desktop | 4 |
| Notebooks | 4 |
| Servidor | 1 |

---

## 5. Camada de Núcleo

A camada de núcleo é composta por dois switches:

- SW-CORE-01
- SW-CORE-02

O roteador (Router0) possui duas interfaces FastEthernet, conectadas individualmente a cada um dos switches de núcleo.

Os switches de núcleo possuem ligação física entre si, preparada para ativação futura de uma agregação de link (link aggregation) de 4 Gbps.

---

## 6. Camada de Distribuição

A camada de distribuição é composta por dois switches:

- SW-DIST-01
- SW-DIST-02

Cada switch de núcleo é conectado individualmente a um switch de distribuição, por meio de interfaces de fibra óptica:

- SW-CORE-01 → SW-DIST-01
- SW-CORE-02 → SW-DIST-02

Essas conexões possuem ligação física preparada para ativação futura de uma agregação de link (link aggregation) de 2 Gbps.

---

## 7. Camada de Borda

A camada de borda é composta por quatro switches (modelo 2960-24TT):

- SW-EDGE-01 — conectado ao SW-DIST-01
- SW-EDGE-02 — conectado ao SW-DIST-01
- SW-EDGE-03 — conectado ao SW-DIST-02
- SW-EDGE-04 — conectado ao SW-DIST-02

Não foram implementados recursos de redundância nessa camada, conforme especificado na atividade.

Os switches de borda são responsáveis por conectar os dispositivos finais à rede.

---

## 8. Dispositivos finais

A rede possui os seguintes dispositivos finais, todos conectados fisicamente (com fio):

| Dispositivo | Conectado a |
|---|---|
| Server0 | SW-EDGE-01 |
| PC0 | SW-EDGE-01 |
| Laptop0 | SW-EDGE-01 |
| PC1 | SW-EDGE-02 |
| Laptop1 | SW-EDGE-02 |
| PC2 | SW-EDGE-03 |
| Laptop2 | SW-EDGE-03 |
| PC3 | SW-EDGE-04 |
| Laptop3 | SW-EDGE-04 |

Total: 4 computadores desktop, 4 notebooks e 1 servidor.

---

## 9. Endereçamento IPv4 — Bônus

Para realização do bônus foi utilizada a rede abaixo:

| Rede | Máscara |
|---|---|
| 192.168.10.0/24 | 255.255.255.0 |

### Tabela de endereçamento

| Dispositivo | Endereço IP |
|---|---|
| PC0 | 192.168.10.10 |
| PC1 | 192.168.10.11 |
| PC1(1) | 192.168.10.12 |
| PC1(2) | 192.168.10.13 |
| Laptop0 | 192.168.10.20 |
| Laptop0(1) | 192.168.10.21 |
| Laptop0(2) | 192.168.10.22 |
| Laptop0(3) | 192.168.10.23 |
| Server0 | 192.168.10.100 |

Todos os dispositivos finais foram conectados por meio físico e configurados para se comunicarem entre si, testado via comando ping.

### Configurações

<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/e762e53a-ccf4-4f40-900d-cb4aa1fe1ece" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/9d01ab4d-7e83-4da0-8cb3-4ce156c30f81" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/9b9a4767-c6a5-442a-bc7c-96783d1111a6" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/e53243eb-50d8-4f2f-86ab-59fdc9483425" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/85c40531-b450-493e-863f-67d8e070461e" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/07d2dab3-369b-4043-96a9-ba66d7913e45" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/a13a11ef-4af9-4fcd-b716-a52e36986fc2" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/c7f9c397-513e-495e-a932-c4b5290ccef4" />
<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/1a477266-27af-422d-a6d7-a652f6aa0fc2" />

### Teste de conectividade

<img width="1920" height="1032" alt="topologia-final" src="https://github.com/user-attachments/assets/f769c62b-1905-4e48-9fdf-53a0da4c2819" />
