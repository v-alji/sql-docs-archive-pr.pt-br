---
title: Criar uma etapa de trabalho de script do ActiveX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ActiveX scripting jobs [SQL Server]
- job steps [Analysis Services]
ms.assetid: e6c46c6b-2d61-4571-bc8e-a831cd6e6302
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6604ba75af7acdd5bd2521433e8310c74150ce8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678567"
---
# <a name="create-an-activex-script-job-step"></a><span data-ttu-id="0f507-102">Create an ActiveX Script Job Step</span><span class="sxs-lookup"><span data-stu-id="0f507-102">Create an ActiveX Script Job Step</span></span>
  <span data-ttu-id="0f507-103">Este tópico descreve como criar e definir uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] etapa de trabalho do Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que executa um script ActiveX usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="0f507-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that executes an ActiveX script by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="0f507-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0f507-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0f507-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="0f507-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0f507-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="0f507-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0f507-107">**Para criar uma etapa de trabalho Transact-SQL usando:**</span><span class="sxs-lookup"><span data-stu-id="0f507-107">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="0f507-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f507-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="0f507-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f507-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="0f507-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0f507-110">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="0f507-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0f507-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0f507-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="0f507-112">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0f507-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="0f507-113">Security</span></span>  
 <span data-ttu-id="0f507-114">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="0f507-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="0f507-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f507-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="0f507-116">Para criar uma etapa de trabalho de Script ActiveX</span><span class="sxs-lookup"><span data-stu-id="0f507-116">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="0f507-117">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="0f507-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0f507-118">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0f507-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="0f507-119">Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="0f507-119">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="0f507-120">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="0f507-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="0f507-121">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f507-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="0f507-122">Na lista **Tipo** , clique em **Script ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="0f507-122">In the **Type** list, click **ActiveX Script**.</span></span>  
  
6.  <span data-ttu-id="0f507-123">Na lista **Executar como** , selecione a conta proxy com as credenciais que o trabalho usará.</span><span class="sxs-lookup"><span data-stu-id="0f507-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="0f507-124">Selecione o **Idioma** no qual o script foi escrito.</span><span class="sxs-lookup"><span data-stu-id="0f507-124">Select the **Language** in which the script was written.</span></span> <span data-ttu-id="0f507-125">Como alternativa, clique em **Outro** e insira o nome da linguagem de script [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX em que o script foi escrito.</span><span class="sxs-lookup"><span data-stu-id="0f507-125">Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.</span></span>  
  
8.  <span data-ttu-id="0f507-126">Na caixa **Comando** , insira a sintaxe de script que será executada para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f507-126">In the **Command** box, enter the script syntax that will be executed for the job step.</span></span> <span data-ttu-id="0f507-127">Como alternativa, clique em **Abrir** e selecione um arquivo que contenha a sintaxe de script.</span><span class="sxs-lookup"><span data-stu-id="0f507-127">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
9. <span data-ttu-id="0f507-128">Clique na página **Avançado** para definir as seguintes opções de etapa de trabalho: a ação a tomar em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tentar executar a etapa e com que frequência.</span><span class="sxs-lookup"><span data-stu-id="0f507-128">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="0f507-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f507-129">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="0f507-130">Para criar uma etapa de trabalho de Script ActiveX</span><span class="sxs-lookup"><span data-stu-id="0f507-130">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="0f507-131">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f507-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0f507-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="0f507-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0f507-133">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0f507-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="0f507-134">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f507-134">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="0f507-135">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0f507-135">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="0f507-136">**Para criar uma etapa de trabalho de Script ActiveX**</span><span class="sxs-lookup"><span data-stu-id="0f507-136">**To create an ActiveX Script job step**</span></span>  
  
 <span data-ttu-id="0f507-137">Use a classe `JobStep` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f507-137">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
