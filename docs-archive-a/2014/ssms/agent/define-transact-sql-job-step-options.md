---
title: Definir opções de etapa de trabalho Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: b2a47057-f6fb-432b-a7b6-5d61f33a5d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc1d6412e52e74ce0c6d987d6189c0c72ffd7df7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679121"
---
# <a name="define-transact-sql-job-step-options"></a><span data-ttu-id="bcf5f-102">Define Transact-SQL Job Step Options</span><span class="sxs-lookup"><span data-stu-id="bcf5f-102">Define Transact-SQL Job Step Options</span></span>
  <span data-ttu-id="bcf5f-103">Este tópico descreve como definir opções para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] etapas de trabalho do Agent no usando o [!INCLUDE[tsql](../../includes/tsql-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-103">This topic describes how to define options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="bcf5f-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="bcf5f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bcf5f-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bcf5f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bcf5f-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="bcf5f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bcf5f-107">**Para definir opções de etapa de trabalho Transact-SQL, usando:**</span><span class="sxs-lookup"><span data-stu-id="bcf5f-107">**To define Transact-SQL job step options, using:** ,</span></span>  
  
     [<span data-ttu-id="bcf5f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bcf5f-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="bcf5f-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="bcf5f-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bcf5f-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bcf5f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bcf5f-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="bcf5f-111">Security</span></span>  
 <span data-ttu-id="bcf5f-112">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="bcf5f-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="bcf5f-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bcf5f-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-transact-sql-job-step-options"></a><span data-ttu-id="bcf5f-114">Para definir opções de etapa de trabalho Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bcf5f-114">To define Transact-SQL job step options</span></span>  
  
1.  <span data-ttu-id="bcf5f-115">No **Pesquisador de Objetos**, expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja editar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-115">In **Object Explorer**, expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bcf5f-116">Clique na página **Etapas** , clique em uma etapa de trabalho e em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-116">Click the **Steps** page, click a job step, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="bcf5f-117">Na caixa de diálogo **Propriedades da Etapa de Trabalho** , confirme que o tipo de trabalho é **Script Transact-SQL (TSQL)** e selecione a página **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-117">On the **Job Step Properties** dialog, confirm that the job type is **Transact-SQL script (TSQL)**, and then select the **Advanced** page.</span></span>  
  
4.  <span data-ttu-id="bcf5f-118">Especifique uma ação a tomar em caso de êxito do trabalho, dentre as opções da lista **Ação ao obter êxito** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-118">Specify an action to take if the job is successful by selecting from the **On success action** list.</span></span>  
  
5.  <span data-ttu-id="bcf5f-119">Especifique um número de tentativas, inserindo um número entre 0 e 9999 na caixa **Tentativas de repetição** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-119">Specify a number of retry attempts by entering a number from 0 to 9999 into the **Retry attempts** box.</span></span>  
  
6.  <span data-ttu-id="bcf5f-120">Especifique um intervalo entre as tentativas, inserindo um número de minutos entre 0 e 9999 na caixa **Intervalo de repetição** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-120">Specify a retry interval by entering a number of minutes from 0 to 9999 into the **Retry interval** box.</span></span>  
  
7.  <span data-ttu-id="bcf5f-121">Especifique uma ação a tomar em caso de falha do trabalho, dentre as opções da lista **Ação ao falhar** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-121">Specify an action to take if the job fails by choosing from the **On failure action** list.</span></span>  
  
8.  <span data-ttu-id="bcf5f-122">Se o trabalho for um script [!INCLUDE[tsql](../../includes/tsql-md.md)] , você poderá escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bcf5f-122">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="bcf5f-123">Inserir o nome de um **Arquivo de saída**.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-123">Enter the name of an **Output file**.</span></span> <span data-ttu-id="bcf5f-124">Por padrão, o arquivo é substituído sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-124">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="bcf5f-125">Se não quiser que o arquivo de saída seja substituído, marque **Anexar saída ao arquivo existente**.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-125">If you do not want the output file overwritten, check **Append output to existing file**.</span></span> <span data-ttu-id="bcf5f-126">Essa opção só está disponível para membros da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-126">This option is only available to members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="bcf5f-127">Observe que o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] não permite aos usuários visualizar arquivos arbitrários no sistema de arquivos e, portanto, não é possível usar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para exibir logs de etapas de trabalho que são gravados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-127">Note that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] does not allow users to view arbitrary files on the file system, so you cannot use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to view job step logs that are written to the file system.</span></span>  
  
    -   <span data-ttu-id="bcf5f-128">Marque **Registrar na tabela** , se desejar registrar a etapa de trabalho em uma tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-128">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="bcf5f-129">Por padrão, o conteúdo da tabela é substituído sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-129">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="bcf5f-130">Se não quiser que o conteúdo da tabela seja substituído, marque **Anexar saída à entrada existente na tabela**.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-130">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="bcf5f-131">Após a execução da etapa de trabalho, o conteúdo dessa tabela pode ser visualizado clicando-se em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-131">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="bcf5f-132">Marque **Incluir saída da etapa no histórico** , se desejar que a saída seja incluída no histórico da etapa.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-132">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="bcf5f-133">A saída será exibida apenas se não houver erros.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-133">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="bcf5f-134">A saída também pode ser truncada.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-134">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="bcf5f-135">Se você for membro da função de servidor fixa **sysadmin** e desejar executar a etapa de trabalho como um logon SQL diferente, selecione esse logon na lista **Executar como usuário** .</span><span class="sxs-lookup"><span data-stu-id="bcf5f-135">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="bcf5f-136">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="bcf5f-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="bcf5f-137">**Para definir opções de etapa de trabalho Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="bcf5f-137">**To define Transact-SQL job step options**</span></span>  
  
 <span data-ttu-id="bcf5f-138">Use a classe `JobStep` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcf5f-138">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
