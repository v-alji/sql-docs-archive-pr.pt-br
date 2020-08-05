---
title: Exibir informações sobre um alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- viewing alerts
- alerts [SQL Server], viewing
- displaying alerts
- status information [SQL Server], alerts
ms.assetid: a0e3a8c4-e3c2-42a5-b2f8-aa06061d3fa6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ee72512a507299e71f13fee689709a9403bb04e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572324"
---
# <a name="view-information-about-an-alert"></a><span data-ttu-id="8f932-102">Exibir informações sobre um alerta</span><span class="sxs-lookup"><span data-stu-id="8f932-102">View Information About an Alert</span></span>
  <span data-ttu-id="8f932-103">Este tópico descreve como exibir informações sobre [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas de agente no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f932-103">This topic describes how to view information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8f932-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8f932-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8f932-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8f932-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8f932-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="8f932-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8f932-107">**Para exibir informações sobre um alerta, usando:**</span><span class="sxs-lookup"><span data-stu-id="8f932-107">**To view information about an alert, using:**</span></span>  
  
     [<span data-ttu-id="8f932-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f932-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8f932-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f932-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8f932-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8f932-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8f932-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8f932-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8f932-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="8f932-112">Permissions</span></span>  
 <span data-ttu-id="8f932-113">Por padrão, os membros da função de servidor fixa **sysadmin** podem exibir as informações sobre um alerta.</span><span class="sxs-lookup"><span data-stu-id="8f932-113">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="8f932-114">Deve ser concedida a outros usuários a função de banco de dados fixa **SQLAgentOperatorRole** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="8f932-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8f932-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f932-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="8f932-116">Para exibir informações sobre um alerta</span><span class="sxs-lookup"><span data-stu-id="8f932-116">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="8f932-117">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor no qual você deseja exibir informações sobre um alerta.</span><span class="sxs-lookup"><span data-stu-id="8f932-117">In **Object Explorer,** click the plus sign to expand the server where you want to view information about an alert.</span></span>  
  
2.  <span data-ttu-id="8f932-118">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="8f932-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="8f932-119">Clique no sinal de adição para expandir a pasta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="8f932-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="8f932-120">Clique com o botão direito do mouse no alerta que tem as informações que você deseja exibir e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8f932-120">Right-click the alert that has the information you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="8f932-121">Para obter mais informações sobre as opções disponíveis contidas na caixa de diálogo _alert_name_**propriedades do alerta** , consulte:</span><span class="sxs-lookup"><span data-stu-id="8f932-121">For more information on the available options contained in the _alert_name_**alert properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="8f932-122">Propriedades do alerta – novo alerta &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="8f932-122">Alert Properties-New Alert &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="8f932-123">Propriedades do alerta – página novo alerta &#40;resposta&#41;</span><span class="sxs-lookup"><span data-stu-id="8f932-123">Alert Properties-New Alert &#40;Response Page&#41;</span></span>](alert-properties-new-alert-response-page.md)  
  
    -   [<span data-ttu-id="8f932-124">Propriedades do alerta: página novas opções de &#40;de alerta&#41;</span><span class="sxs-lookup"><span data-stu-id="8f932-124">Alert Properties: New Alert &#40;Options Page&#41;</span></span>](alert-properties-new-alert-options-page.md)  
  
    -   [<span data-ttu-id="8f932-125">Propriedades do alerta &#40;página Histórico&#41;</span><span class="sxs-lookup"><span data-stu-id="8f932-125">Alert Properties &#40;History Page&#41;</span></span>](alert-properties-history-page.md)  
  
5.  <span data-ttu-id="8f932-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f932-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8f932-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f932-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="8f932-128">Para exibir informações sobre um alerta</span><span class="sxs-lookup"><span data-stu-id="8f932-128">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="8f932-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f932-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8f932-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8f932-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8f932-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8f932-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about the Demo: Sev. 25 Errors alert  
    -- This example assumes that the 'Demo: Sev. 25 Errors' alert exists.  
    USE msdb ;  
    GO  
  
    EXEC sp_help_alert @alert_name = 'Demo: Sev. 25 Errors'  
    GO  
    ```  
  
 <span data-ttu-id="8f932-132">Para obter mais informações, consulte [sp_help_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8f932-132">For more information, see [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span></span>  
  
  
