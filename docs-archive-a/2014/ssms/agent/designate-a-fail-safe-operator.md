---
title: Designar um operador à prova de falhas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- fail-safe operator [SQL Server]
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 0f4eb513-5c0a-4523-974e-e85c1deeb57f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 714ed78875bd289f2fe2d64a5699c59bce58ced0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683907"
---
# <a name="designate-a-fail-safe-operator"></a><span data-ttu-id="70c91-102">Designar um operador à prova de falhas</span><span class="sxs-lookup"><span data-stu-id="70c91-102">Designate a Fail-Safe Operator</span></span>
  <span data-ttu-id="70c91-103">Um operador à prova de falhas é um usuário que recebe o alerta caso o operador designado não possa ser localizado.</span><span class="sxs-lookup"><span data-stu-id="70c91-103">A fail-safe operator is a user who receives the alert if the designated operator cannot be reached.</span></span> <span data-ttu-id="70c91-104">Este tópico descreve como definir um operador à prova de falhas para receber [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notificações de alerta do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70c91-104">This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="70c91-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="70c91-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="70c91-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="70c91-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="70c91-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="70c91-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="70c91-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="70c91-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="70c91-109">**Para designar um operador à prova de falhas usando:**</span><span class="sxs-lookup"><span data-stu-id="70c91-109">**To designate a fail-safe operator, using:**</span></span>  
  
     [<span data-ttu-id="70c91-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70c91-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="70c91-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="70c91-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="70c91-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="70c91-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="70c91-113">As opções Pager e **net send** serão removidas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70c91-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="70c91-114">Evite usar esses recursos em novo trabalho de desenvolvimento e planeje modificar os aplicativos que os usam atualmente.</span><span class="sxs-lookup"><span data-stu-id="70c91-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="70c91-115">Observe que o SQL Server Agent deve ser configurado para usar o Database Mail a fim de enviar notificações por pager ou email a operadores.</span><span class="sxs-lookup"><span data-stu-id="70c91-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="70c91-116">Para obter mais informações, consulte [Atribuir alertas a um operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="70c91-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="70c91-117">gerencia trabalhos de forma fácil e com representação gráfica. Além disso, ele é recomendado para criar e gerenciar a infraestrutura de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="70c91-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="70c91-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="70c91-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="70c91-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="70c91-119">Permissions</span></span>  
 <span data-ttu-id="70c91-120">Somente membros da função de servidor fixa **sysadmin** podem designar operadores à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70c91-120">Only members of the **sysadmin** fixed server role can designate fail-safe operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="70c91-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70c91-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-a-fail-safe-operator"></a><span data-ttu-id="70c91-122">Para designar um operador à prova de falhas</span><span class="sxs-lookup"><span data-stu-id="70c91-122">To designate a fail-safe operator</span></span>  
  
1.  <span data-ttu-id="70c91-123">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor contém operador do SQL Server Agent que você deseja designar como à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70c91-123">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.</span></span>  
  
2.  <span data-ttu-id="70c91-124">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="70c91-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="70c91-125">Na caixa de diálogo **Propriedades do SQL Server Agent –**_server_name_ , em **selecionar uma página**, selecione **sistema de alerta**.</span><span class="sxs-lookup"><span data-stu-id="70c91-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Alert System**.</span></span>  
 
4.  <span data-ttu-id="70c91-126">Em **Operador à prova de falhas**, selecione **Habilitar operador à prova de falhas**.</span><span class="sxs-lookup"><span data-stu-id="70c91-126">Under **Fail-safe operator**, select **Enable fail-safe operator**.</span></span>  
  
5.  <span data-ttu-id="70c91-127">Na lista **Operador** , selecione o operador que você deseja tornar à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70c91-127">In the **Operator** list, select the operator that you want to make a fail-safe.</span></span>  
  
6.  <span data-ttu-id="70c91-128">Marque qualquer uma ou todas as caixas de seleção a seguir para especificar como o operador será notificado: **Email**, **Pager**ou **Net send**.</span><span class="sxs-lookup"><span data-stu-id="70c91-128">Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="70c91-129">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="70c91-129">When finished, click **OK**.</span></span>  
  
  
