---
title: Configurar as propriedades gerais do gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.PolicyManagement.f1
helpviewer_keywords:
- Policy-Based Management, configure properties
ms.assetid: 6d1e0e37-29ea-408a-a055-384984d884be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2efb37fafa29bcb043dedbcfa8719d0092b1c77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680377"
---
# <a name="configure-the-general-properties-of-policy-based-management"></a><span data-ttu-id="ccad3-102">Configurar as propriedades gerais do gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="ccad3-102">Configure the General Properties of Policy-Based Management</span></span>
  <span data-ttu-id="ccad3-103">Este tópico descreve como configurar as propriedades para o Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccad3-103">This topic describes how to configure the properties for Policy-Based Management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ccad3-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ccad3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ccad3-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ccad3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ccad3-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="ccad3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ccad3-107">**Para configurar o Gerenciamento Baseado em Políticas usando:**</span><span class="sxs-lookup"><span data-stu-id="ccad3-107">**To configure Policy-Based Management, using:**</span></span>  
  
     [<span data-ttu-id="ccad3-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccad3-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ccad3-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccad3-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ccad3-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ccad3-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ccad3-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="ccad3-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ccad3-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="ccad3-112">Permissions</span></span>  
 <span data-ttu-id="ccad3-113">Requer a associação à função de banco de dados fixa PolicyAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="ccad3-113">Requires membership in the PolicyAdministratorRole fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ccad3-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccad3-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="ccad3-115">Para configurar o Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="ccad3-115">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="ccad3-116">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja configurar as propriedades do Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="ccad3-116">In **Object Explorer**, click the plus sign to expand the server where you want to configure Policy-Based Management properties.</span></span>  
  
2.  <span data-ttu-id="ccad3-117">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="ccad3-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="ccad3-118">Clique com o botão direito do mouse em **Gerenciamento de Política** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ccad3-118">Right-click **Policy Management** and select **Properties**.</span></span>  
  
     <span data-ttu-id="ccad3-119">As opções a seguir estão disponíveis na caixa de diálogo **Propriedades de Gerenciamento de Política** .</span><span class="sxs-lookup"><span data-stu-id="ccad3-119">The following options are available in **Policy Management Properties** dialog box.</span></span>  
  
     <span data-ttu-id="ccad3-120">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="ccad3-120">**Enabled**</span></span>  
     <span data-ttu-id="ccad3-121">Especifica se o Gerenciamento Baseado em Políticas está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ccad3-121">Specifies whether Policy-Based Management is enabled.</span></span>  
  
     <span data-ttu-id="ccad3-122">**HistoryRetentionInDays**</span><span class="sxs-lookup"><span data-stu-id="ccad3-122">**HistoryRetentionInDays**</span></span>  
     <span data-ttu-id="ccad3-123">Especifica o número de dias que o histórico de avaliação de política deve ser mantido.</span><span class="sxs-lookup"><span data-stu-id="ccad3-123">Specifies the number of days that policy evaluation history should be retained.</span></span> <span data-ttu-id="ccad3-124">Se esse valor for 0 (o padrão), o histórico não será removido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ccad3-124">If this value is 0 (the default), the history will not be automatically removed.</span></span>  
  
     <span data-ttu-id="ccad3-125">**LogOnSuccess**</span><span class="sxs-lookup"><span data-stu-id="ccad3-125">**LogOnSuccess**</span></span>  
     <span data-ttu-id="ccad3-126">Especifica se o Gerenciamento Baseado em Políticas registra em log avaliações de política com êxito.</span><span class="sxs-lookup"><span data-stu-id="ccad3-126">Specifies whether Policy-Based Management logs successful policy evaluations.</span></span>  
  
    -   <span data-ttu-id="ccad3-127">Quando esse valor é false (o padrão), somente são registradas em log as avaliações de política com falha.</span><span class="sxs-lookup"><span data-stu-id="ccad3-127">When this value is false (the default), only failed policy evaluations are logged.</span></span>  
  
    -   <span data-ttu-id="ccad3-128">Quando esse valor é verdadeiro, as avaliações de política bem-sucedidas e com falha são registradas em log.</span><span class="sxs-lookup"><span data-stu-id="ccad3-128">When this value is true, both successful and failed policy evaluations are logged.</span></span>  
  
4.  <span data-ttu-id="ccad3-129">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccad3-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ccad3-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccad3-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="ccad3-131">Para configurar o Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="ccad3-131">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="ccad3-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccad3-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ccad3-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ccad3-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ccad3-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ccad3-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- enables Policy-Based Management   
    USE msdb;  
    GO  
    EXEC dbo.sp_syspolicy_configure   
         @name = N'Enabled',   
         @value = 1;  
    GO  
    ```  
  
 <span data-ttu-id="ccad3-135">Para obter mais informações, veja [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ccad3-135">For more information, see [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span></span>  
  
  
