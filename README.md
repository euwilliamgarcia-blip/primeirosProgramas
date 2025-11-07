# 🕒 Programa de Batimento de Ponto

Um sistema simples e local de **registro de ponto** em Python, com interface gráfica (Tkinter) e geração automática de planilhas **por usuário**.

---

## 📋 Funcionalidades

* Registro de horário de entrada e saída.
* Criação automática de **planilhas mensais** no formato `.csv` (compatível com Excel).
* **Uma planilha por usuário**, armazenada na pasta configurada.
* Exibição de **dias da semana e meses em português**.
* Cálculo automático de horas trabalhadas, saldo de horas e controle de duplas batidas.
* Opção de “Fechar Folha” para verificar total de horas, saldo e possíveis faltas.
* Registro e autenticação de usuários (armazenados em `users.json`).
* Salvamento automático a cada batida (pronto para sincronizar com nuvem).

---

## 💻 Requisitos

### Para Windows

1. **Instalar o Python 3.10 ou superior**

   * Baixe em: [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)
   * **Durante a instalação**, marque a opção:
     ✅ *“Add Python to PATH”*

2. **Instalar as bibliotecas necessárias**

   * Abra o **Prompt de Comando (cmd)** e execute:

     ```bash
     pip install tk openpyxl
     ```
   * O `tk` instala o suporte à interface gráfica (Tkinter).
   * O `openpyxl` é opcional (usado se você quiser exportar para Excel futuramente).

3. **Executar o programa**

   * Coloque o arquivo `batimento_ponto.py` em uma pasta (por exemplo: `Documentos\Ponto`).
   * No Prompt de Comando:

     ```bash
     cd "%USERPROFILE%\Documentos\Ponto"
     python batimento_ponto.py
     ```
   * A janela do programa será aberta automaticamente.

---

## 🧾 Estrutura dos arquivos

Após o primeiro uso, os seguintes arquivos serão criados automaticamente:

```
📂 Ponto/
 ┣ 📄 batimento_ponto.py
 ┣ 📄 users.json
 ┣ 📄 batidas_NomeDoUsuario.csv
 ┗ 📄 config.json (opcional, configurações)
```

* `users.json`: armazena os usuários e senhas.
* `batidas_<usuario>.csv`: planilha com registros do mês e cálculo de horas.

---

## 📆 Colunas da planilha gerada

| Data | Dia da semana | Mês | Hora 1 | Hora 2 | Total (h) | Horas previstas | Saldo (h) |
| ---- | ------------- | --- | ------ | ------ | --------- | --------------- | --------- |

---

## ⚙️ Dicas

* Para **abrir o CSV no Excel**, basta dar duplo clique no arquivo (Excel detecta automaticamente os separadores).
* Se quiser **rodar em outro computador**, copie o arquivo `.py`, o `users.json` e as planilhas `.csv`.
* Para **usar no Linux**, instale o Tkinter com:

  ```bash
  sudo apt install python3-tk
  ```
* Sincronize a pasta com sua nuvem (Google Drive, OneDrive, etc.) para backup automático.

---

## 🔐 Segurança

As senhas atualmente são armazenadas em texto simples.
Você pode ativar a criptografia (bcrypt) — basta pedir que eu adicione isso ao código.

---

## 🧰 Solução de Problemas

| Erro                                             | Causa                             | Solução                                                               |
| ------------------------------------------------ | --------------------------------- | --------------------------------------------------------------------- |
| `ModuleNotFoundError: No module named 'tkinter'` | Tkinter não instalado             | Execute `pip install tk` (ou `sudo apt install python3-tk` no Linux). |
| A janela não abre                                | Python não foi adicionado ao PATH | Reinstale o Python e marque “Add Python to PATH”.                     |
| Arquivo CSV não aparece                          | Nenhuma batida registrada ainda   | Faça pelo menos uma batida de ponto para gerar a planilha.            |

---

