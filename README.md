# KextMaster

KextMaster
O KextMaster é um script Bash para macOS que facilita a instalação de kexts (Kernel Extensions) no diretório /Library/Extensions. Ele oferece uma interface interativa para instalar, substituir e gerenciar kexts, além de registrar logs detalhados para facilitar a depuração.

Funcionalidades

Instalação de Kexts: Instala kexts no diretório /Library/Extensions.
Backup Automático: Faz backup do kext existente antes de substituí-lo.
Validação de Kext: Verifica se o kext é válido e está corretamente assinado.
Recarregamento de Cache: Recarrega o cache do kext após a instalação.
Logs Detalhados: Registra todas as operações em um arquivo de log (/var/log/KextMaster.log).
Menu Interativo: Permite instalar vários kexts sem sair do script.
Requisitos

macOS: Compatível com versões modernas do macOS (Catalina e superiores).
Permissões de Root: O script deve ser executado com permissões de superusuário (root).
Como Usar

Baixe o Script:
Clone este repositório ou baixe o arquivo KextMaster.sh.
Dê Permissão de Execução:
No Terminal, execute:
bash
Copy
chmod +x KextMaster.sh
Execute o Script:
Execute o script com:
bash
Copy
./KextMaster.sh
Siga as Instruções:
O script exibirá um menu interativo. Escolha a opção 1 para instalar um kext.
Insira o caminho completo do kext que deseja instalar.
Confirme o caminho de destino (/Library/Extensions por padrão).
O script fará o backup do kext existente (se houver), instalará o novo kext e recarregará o cache.
Verifique os Logs:
Todos os logs são salvos em /var/log/KextMaster.log.
Exemplo de Uso

bash
Copy
====================================
KextMaster - Menu de Instalação
====================================
1. Instalar um kext
2. Sair
====================================
Escolha uma opção (1 ou 2): 1
🔍 Insira o caminho para o kext que deseja injetar: /Users/henrique/Desktop/EFI/OC/Kexts/USBMap.kext
Deseja injetar o kext em /Library/Extensions? (s/n): s
📂 Copiando /Users/henrique/Desktop/EFI/OC/Kexts/USBMap.kext para /Library/Extensions...
🔧 Ajustando permissões...
♻️ Recarregando cache do kext...
✅ Kext injetado com sucesso em /Library/Extensions!
Logs

Todos os logs são registrados no arquivo /var/log/KextMaster.log. Exemplo de log:

Copy
2025-01-24_13:46:50 - Iniciando instalação de kext em 2025-01-24_13:46:50
2025-01-24_13:46:57 - 📂 Copiando /Users/henrique/Desktop/EFI/OC/Kexts/USBMap.kext para /Library/Extensions...
2025-01-24_13:46:57 - 🔧 Ajustando permissões...
2025-01-24_13:46:57 - ♻️ Recarregando cache do kext...
2025-01-24_13:46:57 - ✅ Kext injetado com sucesso em /Library/Extensions!
Perguntas Frequentes

1. Posso instalar kexts no /System/Library/Extensions?

Não é recomendado. O diretório /System/Library/Extensions é protegido pelo SIP (System Integrity Protection) e só pode ser modificado se o SIP estiver desabilitado. Use /Library/Extensions para kexts de terceiros.
2. O que fazer se o kext não estiver assinado?

O script avisa se o kext não está assinado. Você pode optar por continuar a instalação, mas kexts não assinados podem não funcionar corretamente em versões modernas do macOS.
3. Como desabilitar o SIP?

Reinicie no Recovery Mode (Command + R), abra o Terminal e execute:
bash
Copy
csrutil disable
Atenção: Desabilitar o SIP pode comprometer a segurança do sistema. Reabilite-o após a instalação com:
bash
Copy
csrutil enable
4. Onde os logs são salvos?

Os logs são salvos em /var/log/KextMaster.log.
Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.

