---
title: Agendar um pacote usando SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3d389cce-05af-4e1d-b684-7bbff413c806
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c5ed5e740d263dd5426c06e910dd0e1c595c560
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686319"
---
# <a name="schedule-a-package-by-using-sql-server-agent"></a>Agendar um pacote usando o SQL Server Agent
  O procedimento a seguir fornece as etapas para automatizar a execução do pacote usando uma etapa de trabalho do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent para executar o pacote.  
  
### <a name="to-automate-package-execution-by-using-sql-server-agent"></a>Para automatizar a execução do pacote usando o SQL Server Agent  
  
1.  No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conecte-se à instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em que você deseja criar um trabalho ou a instância que contém o trabalho ao qual deseja adicionar uma etapa.  
  
2.  Expanda o nó [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent no Pesquisador de Objetos e execute uma das tarefas a seguir:  
  
    -   Para criar um trabalho novo, clique com o botão direito do mouse em **Trabalhos** e, em seguida, clique em **Novo Trabalho**.  
  
    -   Para adicionar uma etapa a um trabalho existente, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho e, em seguida, clique em **Propriedades**.  
  
3.  Na página **Geral** , se você estiver criando um novo trabalho, forneça um nome de trabalho, selecione uma categoria e um proprietário e, se desejar, forneça uma descrição do trabalho.  
  
4.  Para disponibilizar o trabalho para agendamento, selecione **Habilitado**.  
  
5.  Para criar uma etapa de trabalho do pacote que deseja agendar, clique em **Etapas**e, em seguida, em **Nova**.  
  
6.  Selecione **Pacote do Integration Services** para o tipo de etapa do trabalho.  
  
7.  Na lista **Executar como** , selecione **Conta de Serviço do SQL Server Agent** ou selecione uma conta proxy com as credenciais que a etapa de trabalho usará. Para obter informações sobre como criar uma conta proxy, consulte [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).  
  
     Usar uma conta proxy em vez de uma **Conta de Serviço do SQL Server Agent** pode resolver problemas comuns que podem ocorrer ao executar um pacote usando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent. Para obter mais informações sobre esses problemas, consulte o [!INCLUDE[msCoName](../includes/msconame-md.md)] Artigo da Base de Dados de Conhecimento, [Um pacote SSIS não é executado quando você chama o pacote do SSIS a partir de uma etapa de trabalho do SQL Server Agent](https://support.microsoft.com/kb/918760).  
  
    > [!NOTE]  
    >  Se a senha for alterada para as credenciais usadas pela conta proxy, será necessário atualizar a senha da credencial. Caso contrário, a etapa do trabalho falhará.  
  
     Para obter informações sobre como configurar a conta de serviço do SQL Server Agent, consulte [Definir a conta de inicialização do serviço para o SQL Server Agent &#40;SQL Server Configuration Manager&#41;](../relational-databases/sql-server-configuration-manager.md).  
  
8.  Na caixa de listagem **Origem do Pacote** , clique na origem do pacote e configure as opções para a etapa do trabalho.  
  
     **A seguinte tabela descreve as possíveis origens do pacote.**  
  
    |Origem do Pacote|Descrição|  
    |--------------------|-----------------|  
    |**Catálogo do SSIS**|Os pacotes armazenados no banco de dados SSISDB. Os pacotes são contidos em projetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que são implantados no servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .|  
    |**SQL Server**|Os pacotes armazenados no banco de dados MSDB. Use o serviço de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para gerenciar esses pacotes.|  
    |**Armazenamento de Pacotes SSIS**|Pacotes que estão armazenados na pasta padrão no computador. A pasta padrão é *\<drive>* :\Arquivos de Programas\Microsoft SQL Server\110\DTS\Pacotes. Use o serviço de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para gerenciar esses pacotes.<br /><br /> Observação: Você pode especificar uma pasta diferente ou pastas adicionais no sistema de arquivos a ser gerenciado pelo serviço de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] modificando o arquivo de configuração para [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]. Para obter mais informações, consulte [Configurando o Serviço Integration Services &#40;Serviço SSIS#41;](service/integration-services-service-ssis-service.md).|  
    |**Sistema de Arquivos**|Pacotes que estão armazenados em qualquer pasta em sua máquina local.|  
  
     **As tabelas seguintes descrevem as opções de configuração que estão disponíveis para a etapa de trabalho segundo a origem do pacote que você selecionou.**  
  
    > [!IMPORTANT]  
    >  Se o pacote estiver protegido por senha, quando você clicar em qualquer uma das guias na página **Geral** da caixa de diálogo **Nova Etapa do Trabalho** , com exceção da guia **Pacote** , precisará digitar a senha na caixa de diálogo **Senha do Pacote** que aparecer. Caso contrário, o trabalho do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent não poderá executar o pacote.  
  
     **Origem do pacote**: Catálogo do SSIS  
  
    |Tab|Opções|  
    |---------|-------------|  
    |**Pacote**|**Servidor**<br /><br /> Digite ou selecione o nome da instância de servidor de banco de dados que hospeda o catálogo de SSISDB.<br /><br /> Quando o **Catálogo do SSIS** é a origem do pacote, você pode fazer logon no servidor que usa somente uma conta de usuário do Microsoft Windows. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não disponível.|  
    ||**Pacote**<br /><br /> Clique no botão de reticências e selecione um pacote.<br /><br /> Você está selecionando um pacote em uma pasta sob o nó de **Catálogos do Integration Services** no **Pesquisador de Objetos**.|  
    |**Parâmetros**<br /><br /> Localizado na guia **Configuração** .|Insira novos valores de parâmetros que estão contidos no pacote. Você pode inserir um valor literal ou usar o valor contido em uma variável de ambiente de servidor que já mapeou para o parâmetro.  **&#42;&#42; importantes &#42;&#42;** Se você mapeou vários parâmetros e/ou propriedades do Gerenciador de conexões para variáveis contidas em vários ambientes, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o Agent exibirá uma mensagem de erro. Para uma execução específica, um pacote pode ser executado somente com os valores contidos em um único ambiente de servidor.<br /><br /> Para digitar o valor literal, clique no botão de reticências ao lado de um parâmetro. A caixa de diálogo **Editar Valor Literal para Execução** é exibida.<br /><br /> Para usar uma variável de ambiente, clique em **Ambiente** e selecione o ambiente que contém a variável que você deseja usar.<br /><br /> <br /><br /> A guia **Parâmetros** exibe os parâmetros que você adicionou quando criou o pacote, por exemplo, usando [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. A guia também exibe os parâmetros que foram adicionados ao pacote quando você converteu o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do modelo de implantação de pacote para o modelo de implantação de projeto. O **Assistente de Conversão de Projetos do Integration Services** permite substituir configurações de pacote por parâmetros.<br /><br /> Para obter informações sobre como criar um ambiente de servidor e mapear uma variável para um parâmetro, consulte [Criar e mapear um ambiente de servidor](../../2014/integration-services/create-and-map-a-server-environment.md).|  
    |**Gerenciadores de conexões**<br /><br /> Localizado na guia **Configuração** .|Altere os valores das propriedades do gerenciador de conexões. Por exemplo, você pode alterar o nome do servidor.<br /><br /> Os parâmetros são gerados automaticamente no servidor do SSIS para as propriedades do gerenciador de conexões.<br /><br /> Para alterar um valor de propriedade, você pode inserir um valor literal ou usar o valor contido em uma variável de ambiente de servidor que já mapeou para a propriedade do gerenciador de conexões. **&#42;&#42; importantes &#42;&#42;** Se você mapeou vários parâmetros e/ou propriedades do Gerenciador de conexões para variáveis contidas em vários ambientes, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o Agent exibirá uma mensagem de erro. Para uma execução específica, um pacote pode ser executado somente com os valores contidos em um único ambiente de servidor.<br /><br /> Para digitar o valor literal, clique no botão de reticências ao lado de um parâmetro. A caixa de diálogo **Editar Valor Literal para Execução** é exibida.<br /><br /> Para usar uma variável de ambiente, clique em **Ambiente** e selecione o ambiente que contém a variável que você deseja usar.<br /><br /> <br /><br /> Para obter informações sobre como criar um ambiente de servidor e mapear uma variável para uma propriedade do gerenciador de conexões, consulte [Criar e mapear um ambiente de servidor](../../2014/integration-services/create-and-map-a-server-environment.md).|  
    |**Avançado**<br /><br /> Localizado na guia **Configuração** .|Defina as seguintes configurações adicionais para a execução do pacote.<br /><br /> <br /><br /> **Substituições de propriedade**: clique em **Adicionar** para inserir um novo valor para uma propriedade de pacote, especifique o caminho da propriedade e indique se o valor da propriedade é confidencial. O servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] criptografa dados confidenciais. Para editar ou remover as configurações de uma propriedade, clique em uma linha na caixa das substituições **Propriedade** e clique em **Editar** ou em **Remover**. Observe que a opção de **substituições de propriedade** destina-se a pacotes com configurações que você atualizou de uma versão anterior do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Pacotes que você cria usando [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] e implanta para o servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] usam parâmetros em vez de configurações. Você pode encontrar o caminho da propriedade seguindo um destes procedimentos:<br /><br /> Copie o caminho da Propriedade do arquivo de configuração XML ( \* . dtsConfig). O caminho é listado na seção Configuração do arquivo como um valor do atributo Caminho. Veja a seguir um exemplo de caminho para a propriedade MaximumErrorCount.<br /><br /> \Package.Properties[MaximumErrorCount]<br /><br /> Execute o **Assistente de configuração de pacotes** e copie os caminhos de propriedade da página final **concluindo o assistente** . Então, você pode cancelar o assistente.|  
    ||**Nível de log**: o nível de log selecionado determina quais informações são exibidas em exibições do SSISDB e em relatórios para o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] servidor. Observe que a seleção do nível de log **Desempenho** ou **Detalhado** pode afetar o desempenho da execução do pacote. Selecione um dos seguintes níveis de log para a execução do pacote:<br /><br /> **Nenhum**: o registro em log está desativado. Apenas o status da execução do pacote é registrado em log.<br /><br /> **Básico**: todos os eventos são registrados, exceto eventos personalizados e de diagnóstico. Este é o valor padrão do nível de log.<br /><br /> **Desempenho**: somente as estatísticas de desempenho e os eventos OnError e OnWarning são registrados em log.<br /><br /> **Verbose**: todos os eventos são registrados, incluindo eventos de diagnóstico e personalizados.<br /><br /> Para saber mais, veja [Habilitar o log para a execução do pacote no servidor SSIS](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).|  
    ||**Despejar em erros**: especifique se os arquivos de despejo de depuração serão gerados quando ocorrer algum erro durante a execução do pacote.<br /><br /> O arquivo contém informações sobre a execução do pacote que pode ajudar a solucionar problemas de execução.<br /><br /> Quando você seleciona essa opção e ocorre um erro durante a execução, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] cria um arquivo .mdmp (arquivo binário) e um arquivo .tmp (arquivo de texto). Por padrão, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] armazena os arquivos na pasta *\<drive>:* \Program Files\Microsoft SQL Server\110\Shared\ErrorDumps.|  
    ||**runtime de 32 bits** Indique se o pacote será executado use doo a versão de 32 bits do utilitário dtexec em um computador de 64 bits que tenha a versão de 64 bits do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent instalada.<br /><br /> Você pode precisar executar o pacote usando uma versão de 32 bits do dtexec, por exemplo, se o pacote usar um provedor OLE DB nativo que não esteja disponível em uma versão de 64 bits. Para obter mais informações, consulte [Considerações do Integration Services sobre versões de 64 bits](https://msdn.microsoft.com/library/ms141766\(SQL.105\).aspx).<br /><br /> Por padrão, quando você seleciona o tipo de etapa de trabalho **Pacote do SQL Server Integration Services** , o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent executa o pacote usando a versão do utilitário dtexec invocada automaticamente pelo sistema. O sistema invoca a versão de 32 bits ou de 64 bits do utilitário, dependendo do processador do computador, e a versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent que está sendo executada no computador.|  
  
     **Origem do pacote**:  SQL Server, Repositório de Pacotes SSIS ou Sistema de Arquivos  
  
     Muitas das opções que você pode definir para pacotes armazenados no SQL Server, no Armazenamento de Pacotes SSIS ou no sistema de arquivos correspondem às opções de linha de comando para o utilitário de prompt de comando `dtexec`. Para obter mais informações sobre as opções de linha de comando e utilitário, consulte [Utilitário dtexec](packages/dtexec-utility.md).  
  
    |Tab|Opções|  
    |---------|-------------|  
    |**Pacote**<br /><br /> Estas são as opções da guia para pacotes que estão armazenados no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou no Armazenamento de pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] .|**Servidor**<br /><br /> Digite ou selecione o nome da instância do servidor do banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou do serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .|  
    ||**Usar Autenticação do Windows**<br /><br /> Selecione esta opção para fazer logon no servidor usando uma conta de usuário do Microsoft Windows.|  
    ||**Usar Autenticação do SQL Server**<br /><br /> Quando um usuário se conecta com um nome de logon e senha especificados em uma conexão não confiável, o próprio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] efetua a autenticação verificando se foi definida uma conta de logon do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e se a senha especificada corresponde a uma senha registrada previamente. Se o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não localizar a conta de login, ocorrerá uma falha na autenticação e o usuário receberá uma mensagem de erro.|  
    ||**Nome de usuário**|  
    ||**Senha**|  
    ||**Pacote**<br /><br /> Clique no botão de reticências e selecione o pacote.<br /><br /> Você está selecionando um pacote em uma pasta sob o nó de **Pacotes Armazenados** no **Pesquisador de Objetos**.|  
    |**Pacote**<br /><br /> Estas são as opções da guia para pacotes que estão armazenados no sistema de arquivos.|**Pacote**<br /><br /> Digite o caminho completo do arquivo do pacote ou clique no botão de reticências para selecionar o pacote.|  
    |**Configurações**|Adicione um arquivo de configuração XML para executar o pacote com uma configuração específica. Use uma configuração de pacote para atualizar os valores das propriedades do pacote no runtime.<br /><br /> Essa opção corresponde à opção **/ConfigFile** para `dtexec` .<br /><br /> Para compreender como são aplicadas as configurações de pacote, consulte [Package Configurations](../../2014/integration-services/package-configurations.md). Para obter informações sobre como criar uma configuração de pacote, consulte [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).|  
    |**Arquivos de comando**|Especifique opções adicionais que deseja executar com `dtexec` em um arquivo separado.<br /><br /> Por exemplo, você pode incluir um arquivo que contém a opção de /Dump *errorcode* para gerar arquivos de despejo de depuração quando um ou mais eventos especificados ocorrerem durante a execução do pacote.<br /><br /> Você pode executar um pacote com conjuntos diferentes de opções criando vários arquivos e especificando o arquivo apropriado usando a opção **Arquivos de Comando** .<br /><br /> A opção **arquivos de comando** corresponde à `/CommandFile` opção para `dtexec` .|  
    |**Fontes de dados**|Exiba os gerenciadores de conexões contidos no pacote. Para modificar uma cadeia de caracteres de conexão, clique no gerenciador de conexões e depois na cadeia de conexões.<br /><br /> Essa opção corresponde à opção de `/Connection` para `dtexec`.|  
    |**Opções de Execução**|**Reprovar o pacote nos avisos de validação**<br /> Indica se uma mensagem de aviso é considerada um erro. Se você selecionar essa opção e ocorrer um aviso durante a validação, o pacote falhará durante a validação. Essa opção corresponde à opção de `/WarnAsError` para `dtexec`.<br /><br /> **Validar pacote sem executar**<br /> Indica se a execução do pacote é interrompida depois da fase de validação, sem executar realmente o pacote. Essa opção corresponde à opção de `/Validate` para `dtexec`.<br /><br /> **Substituir a propriedade MacConcurrentExecutables**<br /> Especifica o número de arquivos executáveis que o pacote pode executar simultaneamente. O valor de -1 significa que o pacote pode executar um número máximo de arquivos executáveis igual ao número total de processadores no computador que executa o pacote mais dois. Essa opção corresponde à opção de `/MaxConcurrent` para `dtexec`.<br /><br /> **Ativar pontos de verificação do pacote**<br /> Indica se o pacote usará pontos de verificação durante sua execução. Para saber mais, confira [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).<br /><br /> Essa opção corresponde à opção de `/CheckPointing` para `dtexec`.<br /><br /> **Substituir opções de reinicialização**<br /> Indica se um novo valor está definido para a propriedade `CheckpointUsage` no pacote. Selecione um valor na caixa de listagem **Opção de Reinicialização** .<br /><br /> Essa opção corresponde à opção de `/Restart` para `dtexec`.<br /><br /> **Use o runtime de 32 bits**<br /> Indique se o pacote será executado usando a versão de 32 bits do utilitário dtexec em um computador de 64 bits que tenha a versão de 64 bits do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent instalada.<br /><br /> Você pode precisar executar o pacote usando uma versão de 32 bits do dtexec, por exemplo, se o pacote usar um provedor OLE DB nativo que não esteja disponível em uma versão de 64 bits. Para obter mais informações, consulte [Considerações do Integration Services sobre versões de 64 bits](https://msdn.microsoft.com/library/ms141766\(SQL.105\).aspx).<br /><br /> Por padrão, quando você seleciona o tipo de etapa de trabalho **Pacote do SQL Server Integration Services** , o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent executa o pacote usando a versão do utilitário dtexec invocada automaticamente pelo sistema. O sistema invoca a versão de 32 bits ou de 64 bits do utilitário, dependendo do processador do computador, e a versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent que está sendo executada no computador.|  
    |**Logging**|Associe um provedor de logs à execução do pacote.<br /><br /> **Provedor de log SSIS log para arquivos de Texto**<br /> Grava entradas de log em arquivos de texto ASCII<br /><br /> **Provedor de log SSIS log para o SQL Server**<br /> Escreve entradas de log na tabela sysssislog do banco de dados MSDB.<br /><br /> **Provedor de log SSIS para o SQL Server Profiler**<br /> Grava rastreamentos que você pode exibir usando o SQL Server Profiler.<br /><br /> **Provedor de log SSIS para o Log de Eventos do Windows**<br /> Grava entradas de log no log de aplicativos do log de eventos do Windows Event.<br /><br /> **Provedor de log SSIS log para arquivos XML**<br /> Grava arquivos de log em um arquivo XML.<br /><br /> Para o arquivo de texto, arquivo XML e os provedores de log do Profiler [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , você está selecionando os gerenciadores de conexões de arquivos que estão contidos no pacote. Para o provedor de log do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , você está selecionando um gerenciador de conexões OLE DB que está contido no pacote.<br /><br /> Essa opção corresponde à opção de `/Logger` para `dtexec`.|  
    |**Valores definidos**|Substitua uma configuração de propriedade do pacote. Na caixa **Propriedades** , digite os valores nas colunas **Caminho da Propriedade** e **Valor** . Depois que você inserir valores para uma propriedade, uma linha vazia será exibida na caixa **Propriedades** para permitir que você insira valores para outra propriedade.<br /><br /> Para remover uma propriedade da caixa Propriedades, clique na linha e depois em **Remover**.<br /><br /> Você pode encontrar o caminho da propriedade seguindo um dos procedimentos a seguir.<br /><br /> Copie o caminho da Propriedade do arquivo de configuração XML ( \* . dtsConfig). O caminho é listado na seção Configuração do arquivo como um valor do atributo Caminho. Veja a seguir um exemplo de caminho para a propriedade MaximumErrorCount.<br /><br /> \Package.Properties[MaximumErrorCount]<br /><br /> Execute o **Assistente de configuração de pacotes** e copie os caminhos de propriedade da página final **concluindo o assistente** . Então, você pode cancelar o assistente.|  
    |**Verificação**|**Executar apenas pacotes assinados**<br /> Indica se a assinatura do pacote foi verificada. Se o pacote não for assinado ou a assinatura não for válida, o pacote falhará. Essa opção corresponde à opção de `/VerifySigned` para `dtexec`.<br /><br /> **Verificar a compilação do pacote**<br /> Indica se o número da compilação do pacote será verificado no número da compilação inserido na caixa **Compilar** ao lado dessa opção. Se uma ocorrer um erro de correspondência, o pacote não será executado. Essa opção corresponde à opção de `/VerifyBuild` para `dtexec`.<br /><br /> **Verificar ID do pacote**<br /> Indica se o GUID do pacote será verificado comparando-o ao ID do pacote inserido na caixa **ID do Pacote** ao lado dessa opção. Essa opção corresponde à opção de `/VerifyPackageID` para `dtexec`.<br /><br /> **Verificar ID da versão**<br /> Indica se o GUID da versão do pacote será verificada comparando o ID da versão inserido na caixa **ID da Versão** ao lado dessa opção. Essa opção corresponde à opção de `/VerifyVersionID` para `dtexec`.|  
    |**Linha de comando**|Modifique as opções de linha de comando para dtexec. Para obter mais informações sobre as opções, consulte [dtexec Utility](packages/dtexec-utility.md).<br /><br /> Dica: você pode copiar a linha de comando para uma janela de prompt de comando, adicionar `dtexec` e executar o pacote da linha de comando. Essa é uma forma fácil de gerar o texto da linha de comando.<br /><br /> **Restaurar as opções originais**<br /> Use as opções de linha de comando que você definiu nas guias **Pacote**, **Configurações**, **Arquivos de comando**, **Fontes de dados**, **Opções de execução**, **Logging**, **Definir valores**e **Verificação** da caixa de diálogo **Propriedades do Trabalho** .<br /><br /> **Editar o comando manualmente**<br /> Digite opções adicionais de linha de comando na caixa **Linha de Comando** .<br /><br /> Antes de clicar em **OK** para salvar suas alterações na etapa de trabalho, você pode remover todas as opções adicionais que digitou na caixa **Linha de Comando** clicando em **Restaurar as Opções Originais**.|  
  
9. Clique em **OK** para salvar as configurações e feche a caixa de diálogo **Nova Etapa de Trabalho** .  
  
    > [!NOTE]  
    >  Para pacotes armazenados no **Catálogo do SSIS**, o botão **OK** é desativado quando há um parâmetro não resolvido ou uma configuração de propriedade do gerenciador de conexões. Uma configuração não resolvida ocorre quando você está usando um valor contido em uma variável de ambiente de servidor para definir o parâmetro ou a propriedade e uma das condições a seguir é atendida.  
    >   
    >  -   A caixa de seleção **Ambiente** na guia **Configuração** não está marcada.  
    > -   O ambiente de servidor que contém a variável não está selecionado na caixa de listagem na guia **Configuração** .  
  
10. Para criar uma agenda para uma etapa de trabalho, clique em **Agendas** no painel **Selecionar uma Página** . Para obter informações sobre como configurar uma agenda, consulte [Schedule a Job](../ssms/agent/schedule-a-job.md).  
  
    > [!TIP]  
    >  Ao nomear a agenda, use um nome que seja exclusivo e descritivo para que você possa distinguir mais facilmente a agenda de outras agendas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.  
  
## <a name="see-also"></a>Consulte Também  
 [Execução de projetos e pacotes](packages/run-integration-services-ssis-packages.md)  
  
  