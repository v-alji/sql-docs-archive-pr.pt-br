---
title: Exibir informações de etapa de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568337"
---
# <a name="view-job-step-information"></a><span data-ttu-id="61586-102">View Job Step Information</span><span class="sxs-lookup"><span data-stu-id="61586-102">View Job Step Information</span></span>
  <span data-ttu-id="61586-103">Este tópico descreve como exibir detalhes de etapa de trabalho na caixa de diálogo Propriedades da Etapa de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="61586-103">This topic describes how to view job step details in the Job Step Properties dialog.</span></span> <span data-ttu-id="61586-104">Ela também inclui informações sobre a exibição da saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="61586-104">It also includes information about viewing job step output.</span></span>  
  
-   <span data-ttu-id="61586-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="61586-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="61586-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="61586-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="61586-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="61586-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="61586-108">**Para exibir informações de etapas de trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="61586-108">**To view job step information, using:**</span></span>  
  
     [<span data-ttu-id="61586-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61586-109">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61586-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="61586-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="61586-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="61586-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="61586-112">Se a etapa de trabalho tiver sido configurada de modo a gravar sua saída em uma tabela ou arquivo e o trabalho tiver sido executado pelo menos uma vez, a saída poderá ser vista na página **Avançado** da caixa de diálogo **Propriedades da Etapa de Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="61586-112">If the job step has been configured to write its output to a table or file and the job has run at least once, you can view its output on the **Advanced** page of the **Job Step Properties** dialog.</span></span> <span data-ttu-id="61586-113">Quando um trabalho ou etapa de trabalho é excluído, o log de saída é excluído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="61586-113">When a job or job step is deleted, the output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61586-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="61586-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="61586-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="61586-115">Permissions</span></span>  
 <span data-ttu-id="61586-116">Você só pode exibir trabalhos de sua propriedade, a não ser que você seja membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="61586-116">You can view only those jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="61586-117">Membros dessa função podem exibir todos os trabalhos e detalhes de etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="61586-117">Members of this role can view all jobs and job step details.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="61586-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61586-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-step-information"></a><span data-ttu-id="61586-119">Para exibir informações de etapas de trabalho</span><span class="sxs-lookup"><span data-stu-id="61586-119">To view job step information</span></span>  
  
1.  <span data-ttu-id="61586-120">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="61586-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="61586-121">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que contém a etapa que deseja exibir e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="61586-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that contains the job step to be viewed, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="61586-122">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** .</span><span class="sxs-lookup"><span data-stu-id="61586-122">In the **Job Properties** dialog, click the **Steps** page.</span></span>  
  
4.  <span data-ttu-id="61586-123">Clique na etapa de trabalho a ser exibida e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="61586-123">Click the job step to be viewed, and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="61586-124">Na página **Geral** da caixa de diálogo **Propriedades da Etapa de Trabalho** , é possível visualizar o tipo de etapa de trabalho e o que ela faz.</span><span class="sxs-lookup"><span data-stu-id="61586-124">On the **General** page of the **Job Step Properties** dialog, you can view the type of job step and what it does.</span></span>  
  
6.  <span data-ttu-id="61586-125">Clique na página **Avançado** para visualizar as ações que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent toma em caso de êxito ou falha da etapa, quantas vezes a etapa deve ser tentada, onde deve ser gravada sua saída e o usuário com o qual ela é executada.</span><span class="sxs-lookup"><span data-stu-id="61586-125">Click the **Advanced** page to view the actions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes if the job step succeeds or fails, how many times the job step should be attempted, where the job step output is written, and the user the job step runs as.</span></span>  
  
#### <a name="to-view-job-step-output"></a><span data-ttu-id="61586-126">Para exibir a saída da etapa de trabalho</span><span class="sxs-lookup"><span data-stu-id="61586-126">To view job step output</span></span>  
  
1.  <span data-ttu-id="61586-127">Na caixa de diálogo **Propriedades da Etapa de Trabalho** , clique na página **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="61586-127">In the **Job Step Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="61586-128">Dependendo da versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a que está conectado, você poderá visualizar o arquivo ou a tabela de saída da etapa de trabalho, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="61586-128">Depending on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connected to, you can view either the job step output file or table as follows:</span></span>  
  
    -   <span data-ttu-id="61586-129">Se estiver conectado ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou versão posterior, você só poderá clicar em **Exibir** se a opção **Registrar em tabela** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="61586-129">When you are connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later, you can click **View** only when **Log to table** is checked.</span></span> <span data-ttu-id="61586-130">Nesse caso, a saída da etapa de trabalho será gravada na tabela **sysjobstepslogs** do banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="61586-130">In this case, the job step output is written to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
    -   <span data-ttu-id="61586-131">O botão **Exibir** encontra-se desabilitado quando a saída da etapa de trabalho é gravada em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="61586-131">The **View** button is disabled when job step output is written to a file.</span></span> <span data-ttu-id="61586-132">Para visualizar o arquivo de saída da etapa de trabalho, use o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="61586-132">To view a job step output file, use Notepad.</span></span>  
  
  
