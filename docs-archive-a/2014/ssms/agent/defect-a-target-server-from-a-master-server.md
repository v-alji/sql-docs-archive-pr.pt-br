---
title: Remover um servidor de destino de um servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
ms.assetid: a6da262b-7b38-4ce4-bfd6-6a557c6e8a84
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b17703fa87f5c0d3e7146a1660ac1ca7c7c1d81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680299"
---
# <a name="defect-a-target-server-from-a-master-server"></a><span data-ttu-id="91631-102">Remover um servidor de destino de um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="91631-102">Defect a Target Server from a Master Server</span></span>
  <span data-ttu-id="91631-103">Este tópico descreve como remover um servidor de destino de um servidor mestre no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="91631-103">This topic describes how to defect a target server from a master server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="91631-104">Execute este procedimento a partir do servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="91631-104">Run this procedure from the target server.</span></span>  
  
 <span data-ttu-id="91631-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="91631-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="91631-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="91631-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="91631-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="91631-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="91631-108">**Para remover um servidor de destino usando:**</span><span class="sxs-lookup"><span data-stu-id="91631-108">**To defect a target server, using:**</span></span>  
  
     [<span data-ttu-id="91631-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="91631-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="91631-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="91631-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="91631-111">SMO</span><span class="sxs-lookup"><span data-stu-id="91631-111">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="91631-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="91631-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="91631-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="91631-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="91631-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="91631-114">Permissions</span></span>  
 <span data-ttu-id="91631-115">Para executar este procedimento armazenado, o usuário deve ser um membro da função de servidor fixa `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="91631-115">To execute this stored procedure, a user must be a member of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="91631-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="91631-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="91631-117">Para remover um servidor de destino de um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="91631-117">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="91631-118">No **Pesquisador de Objetos**, expanda um servidor que esteja configurado como servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="91631-118">In **Object Explorer**, expand a server that is configured as a target server.</span></span>  
  
2.  <span data-ttu-id="91631-119">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="91631-119">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.</span></span>  
  
3.  <span data-ttu-id="91631-120">Clique em **Sim** para confirmar que deseja remover o servidor de destino de um servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="91631-120">Click **Yes** to confirm that you want to defect this target server from a master server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="91631-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="91631-121">Using Transact-SQL</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="91631-122">Para remover um servidor de destino de um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="91631-122">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="91631-123">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91631-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="91631-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="91631-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="91631-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="91631-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```sql
sp_msx_defect ;  
```  
  
 <span data-ttu-id="91631-126">Para obter mais informações, consulte [sp_msx_defect &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="91631-126">For more information, see [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="91631-127">Usando o SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="91631-127">Using SQL Server Management Objects (SMO)</span></span>  
 <span data-ttu-id="91631-128">Use a `MsxDefect Method`.</span><span class="sxs-lookup"><span data-stu-id="91631-128">Use the `MsxDefect Method`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91631-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91631-129">See Also</span></span>  
 <span data-ttu-id="91631-130">[Criar um ambiente multisservidor](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="91631-130">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="91631-131">[Administração automatizada em toda a empresa](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="91631-131">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="91631-132">Remover vários servidores de destino de um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="91631-132">Defect Multiple Target Servers from a Master Server</span></span>](defect-multiple-target-servers-from-a-master-server.md)  
