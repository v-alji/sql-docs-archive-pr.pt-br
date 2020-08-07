---
title: Especificar um servidor de destino&#39;o local (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], location
ms.assetid: 511ff311-21f5-4f2f-839f-b4deee26ec98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 938528ab78f0f457cde69d8fd4d5432cc14a79b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576109"
---
# <a name="specify-a-target-server39s-location-sql-server-management-studio"></a><span data-ttu-id="4022f-102">Especificar o local de um servidor de destino (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4022f-102">Specify a Target Server&#39;s Location (SQL Server Management Studio)</span></span>
  <span data-ttu-id="4022f-103">Este tópico descreve como especificar o local de um servidor de destino em uma configuração de administração multisservidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4022f-103">This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4022f-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4022f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4022f-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4022f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4022f-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4022f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4022f-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="4022f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4022f-108">**Para especificar o local de um servidor de destino usando:**</span><span class="sxs-lookup"><span data-stu-id="4022f-108">**To specify a target server's location, using:**</span></span>  
  
     [<span data-ttu-id="4022f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4022f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4022f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4022f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4022f-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4022f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4022f-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4022f-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4022f-113">Executar essa ação edita o registro.</span><span class="sxs-lookup"><span data-stu-id="4022f-113">Performing this action edits the registry.</span></span> <span data-ttu-id="4022f-114">A edição manual do registro não é recomendada, pois alterações incorretas ou não apropriadas podem causar sérios problemas de configuração para o sistema.</span><span class="sxs-lookup"><span data-stu-id="4022f-114">Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system.</span></span> <span data-ttu-id="4022f-115">Portanto, apenas usuários experientes deveriam usar o programa Editor do Registro para editar o registro.</span><span class="sxs-lookup"><span data-stu-id="4022f-115">Therefore, only experienced users should use the Registry Editor program to edit the registry.</span></span> <span data-ttu-id="4022f-116">Para obter mais informações, consulte a documentação do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4022f-116">For more information, see the Microsoft Windows documentation.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4022f-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="4022f-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4022f-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="4022f-118">Permissions</span></span>  
 <span data-ttu-id="4022f-119">Exige associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4022f-119">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4022f-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4022f-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="4022f-121">Para especificar o local de um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="4022f-121">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="4022f-122">No **Pesquisador de Objetos,** clique no sinal de adição para expandir o servidor mestre no qual você deseja especificar o local de um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="4022f-122">In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.</span></span>  
  
2.  <span data-ttu-id="4022f-123">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e selecione **Gerenciar Servidores de Destino**.</span><span class="sxs-lookup"><span data-stu-id="4022f-123">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="4022f-124">Clique com o botão direito do mouse em um servidor de destino e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4022f-124">Right-click a target server and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="4022f-125">Na caixa **Local** , insira um local para o servidor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4022f-125">In the **Location** box, enter a location for the server, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4022f-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4022f-126">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="4022f-127">Para especificar o local de um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="4022f-127">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="4022f-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4022f-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4022f-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4022f-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4022f-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4022f-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2012',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
 <span data-ttu-id="4022f-131">Para obter mais informações, consulte [sp_msx_enlist &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4022f-131">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
  
