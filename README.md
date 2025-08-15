# Maestro

Este repositório contém fluxos (`flows/`) e exemplos de testes para serem executados com [Maestro](https://maestro.mobile.dev), automatizando aplicativos Android como `Swag Labs Mobile App`.

## Estrutura do Repositório

Maestro/
├── apps/         # APKs ou código do app para testes (se houver)
├── flows/        # Testes .yaml escritos para Maestro
└── README.md     # Este arquivo

---

##  Pré-requisitos

### 1. Android SDK + Emulador ou Dispositivo
- Ter o **SDK do Android** instalado (via Android Studio ou Command Line Tools).
- Emulador Android configurado ou dispositivo físico conectado.

### 2. Maestro CLI
Instale o **Maestro** para rodar os testes declarativos em YAML.

---

##  Instalação e Execução

###  Linux / Ubuntu (inclui WSL)

#### A. Instalar o Maestro
Se tiver **Homebrew instalado** (via `brew`):
```
brew install mobile-dev-inc/tap/maestro
```

Ou instale com o script oficial:
```
curl -Ls "https://get.maestro.mobile.dev" | bash
```

Depois, confirme:
```
maestro --version
```

#### B. Fixes importantes (GTK & Snap)

Se você enfrentar erros como:
```
Unable to locate theme engine in module_path: "adwaita", "pixmap", "murrine"
symbol lookup error: libpthread.so.0: undefined symbol: __libc_pthread_init
```
Use a versão **não-Snap** do Maestro (via brew ou script), pois a versão Snap causa conflitos com a GLIBC.

#### C. Executar teste
No terminal:
```
adb devices           # confirmar que o emulador está conectado
maestro test flows/   # executa todos os fluxos .yaml
```

---

###  Windows

#### A. Instalar Maestro

1. Baixe o binário `.exe` em:  
   https://github.com/mobile-dev-inc/maestro/releases
2. Descompacte e adicione o diretório ao `PATH` (variável de ambiente do sistema).

#### B. Confirmar Instalação
```
maestro --version
```

#### C. Executar teste
Certifique-se de que seu emulador ou dispositivo Android esteja conectado:
```
adb devices
maestro test flows\
```
