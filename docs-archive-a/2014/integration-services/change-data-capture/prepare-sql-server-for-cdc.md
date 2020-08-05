---
title: Preparar o SQL Server para CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- prepSqlSrv
ms.assetid: 20b51dbf-a545-4234-87ae-4228268a0fb2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dafa29d9bdb0c27decb605398a6d1cfe383427e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570818"
---
# <a name="prepare-sql-server-for-cdc"></a><span data-ttu-id="bdd57-102">Preparar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="bdd57-102">Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="bdd57-103">O serviço Oracle CDC exige que todas as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino contenham o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="bdd57-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="bdd57-104">Você cria este banco de dados usando a ação Preparar ação do SQL Server no Console de Configuração do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="bdd57-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.</span></span> <span data-ttu-id="bdd57-105">Isto cria um script especial que é executado para criar as tabelas exigidas, os procedimentos armazenados e outros artefatos necessários para este banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bdd57-105">This creates a special script that is run to create the required tables, stored procedures, and other required artifacts for this database.</span></span> <span data-ttu-id="bdd57-106">Esta tarefa só é feita uma vez para cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="bdd57-106">This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="bdd57-107">Para obter mais informações sobre o banco de dados MSXDBCDC, consulte O banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="bdd57-107">For more information about the MSXDBCDC database, see The MSXDBCDC Database.</span></span>  
  
 <span data-ttu-id="bdd57-108">No Console de Configuração do Serviço CDC, clique em **Preparar SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bdd57-108">In the CDC Service Configuration Console, click **Prepare SQL Server**.</span></span> <span data-ttu-id="bdd57-109">Se esta opção não estiver disponível, verifique se a opção **Serviços Locais CDC** está marcada no painel esquerdo do console.</span><span class="sxs-lookup"><span data-stu-id="bdd57-109">If this option is not available, make sure that **Local CDC Services** is selected in the left pane of the console.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bdd57-110">Opções</span><span class="sxs-lookup"><span data-stu-id="bdd57-110">Options</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="bdd57-111">Nome do servidor</span><span class="sxs-lookup"><span data-stu-id="bdd57-111">Server Name</span></span>  
 <span data-ttu-id="bdd57-112">Digite o nome do servidor em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está localizado.</span><span class="sxs-lookup"><span data-stu-id="bdd57-112">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="bdd57-113">Autenticação</span><span class="sxs-lookup"><span data-stu-id="bdd57-113">Authentication</span></span>  
 <span data-ttu-id="bdd57-114">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="bdd57-114">Select one of the following:</span></span>  
  
-   <span data-ttu-id="bdd57-115">**Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="bdd57-115">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="bdd57-116">**Autenticação do SQL Server**: se você selecionar esta opção, deverá digitar o **Nome de Usuário** e **Senha** para o usuário no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="bdd57-116">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="bdd57-117">Para preparar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para Oracle CDC, o logon deve ter permissão de gravação no banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="bdd57-117">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="bdd57-118">Insira as credenciais para um logon que tem permissão de gravação no banco de dados MSXDBCDC, como um membro da função `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="bdd57-118">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
### <a name="options"></a><span data-ttu-id="bdd57-119">Opções</span><span class="sxs-lookup"><span data-stu-id="bdd57-119">Options</span></span>  
 <span data-ttu-id="bdd57-120">Clique na seta para exibir opções disponíveis a serem configuradas.</span><span class="sxs-lookup"><span data-stu-id="bdd57-120">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="bdd57-121">Você pode escolher deixar estas opções com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="bdd57-121">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="bdd57-122">As opções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="bdd57-122">The available options are:</span></span>  
  
-   <span data-ttu-id="bdd57-123">**Tempo limite da conexão**: Digite o tempo (em segundos) que o Serviço CDC para Oracle espera por uma conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de exceder o tempo limite. O valor padrão é **15**.</span><span class="sxs-lookup"><span data-stu-id="bdd57-123">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="bdd57-124">**Tempo limite de execução**: Digite o tempo (em segundos) que o Serviço do Windows do Oracle CDC espera que um comando seja executado antes de exceder o tempo limite. O valor padrão é **30**.</span><span class="sxs-lookup"><span data-stu-id="bdd57-124">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="bdd57-125">**Criptografar conexão**: selecione **Criptografar Conexão** para a comunicação entre o Serviço Oracle CDC e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="bdd57-125">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="bdd57-126">**Avançado**: digite as propriedades de conexão adicionais, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bdd57-126">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
### <a name="view-script"></a><span data-ttu-id="bdd57-127">Exibir script</span><span class="sxs-lookup"><span data-stu-id="bdd57-127">View Script</span></span>  
 <span data-ttu-id="bdd57-128">Clique em **Exibir Script** para exibir uma versão somente leitura do script de instalação.</span><span class="sxs-lookup"><span data-stu-id="bdd57-128">Click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="bdd57-129">Um administrador do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode copiar este script no Console de Gerenciamento do SQL Server para editá-lo, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="bdd57-129">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the SQL Server Management Console to edit it, if necessary.</span></span> <span data-ttu-id="bdd57-130">Para obter mais informações sobre o Script Preparar SQL Server, consulte [Script de visualização Preparar SQL Server para Oracle CDC](prepare-sql-server-for-oracle-cdc-view-script.md).</span><span class="sxs-lookup"><span data-stu-id="bdd57-130">For more information about the Prepare SQL Server Script, see [Prepare SQL Server for Oracle CDC-View Script](prepare-sql-server-for-oracle-cdc-view-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd57-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdd57-131">See Also</span></span>  
 <span data-ttu-id="bdd57-132">[Como trabalhar com os serviços CDC](work-with-cdc-services.md) </span><span class="sxs-lookup"><span data-stu-id="bdd57-132">[How to Work with CDC Services](work-with-cdc-services.md) </span></span>  
 [<span data-ttu-id="bdd57-133">Como preparar o SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="bdd57-133">How to Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
