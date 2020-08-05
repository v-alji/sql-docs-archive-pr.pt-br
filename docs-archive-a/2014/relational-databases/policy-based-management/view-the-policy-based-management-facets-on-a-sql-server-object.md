---
title: Exibir as facetas de Gerenciamento Baseado em Políticas em um objeto do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facets
ms.assetid: 5f423b9f-a6c4-41a7-9d8d-8f4926ce1fb4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9137971a79e9e5a18e0ef5d901184133a4c3eff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571982"
---
# <a name="view-the-policy-based-management-facets-on-a-sql-server-object"></a><span data-ttu-id="37318-102">Exibir as facetas de Gerenciamento Baseado em Políticas em um objeto do SQL Server</span><span class="sxs-lookup"><span data-stu-id="37318-102">View the Policy-Based Management Facets on a SQL Server Object</span></span>
  <span data-ttu-id="37318-103">Este tópico descreve como exibir todas as facetas do Gerenciamento Baseado em Políticas aplicadas a um objeto do SQL Server específico no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37318-103">This topic describes how to view all of the Policy-Based Management facets applied to a specific SQL Server object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="37318-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="37318-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="37318-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="37318-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="37318-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="37318-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="37318-107">**Para exibir todas as facetas em um objeto, usando:**</span><span class="sxs-lookup"><span data-stu-id="37318-107">**To view all of the facets in an object, using:**</span></span>  
  
     [<span data-ttu-id="37318-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37318-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37318-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="37318-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37318-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="37318-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37318-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="37318-111">Permissions</span></span>  
 <span data-ttu-id="37318-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="37318-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37318-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37318-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-all-of-the-facets-in-an-object"></a><span data-ttu-id="37318-114">Para exibir todas as facetas em um objeto</span><span class="sxs-lookup"><span data-stu-id="37318-114">To view all of the facets in an object</span></span>  
  
1.  <span data-ttu-id="37318-115">No Pesquisador de Objetos, clique com o botão direito do mouse em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um objeto de instância, banco de dados ou objeto de banco de dados e clique em **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="37318-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="37318-116">Na caixa de diálogo **Exibir Facetas -**_nome_do_objeto_, na lista **Faceta**, selecione uma faceta para exibir suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="37318-116">In the **View Facets -**_object_name_ dialog box, in the **Facet** list, select a facet to view its properties.</span></span> <span data-ttu-id="37318-117">Para obter mais informações sobre as opções disponíveis nesta caixa de diálogo, consulte [View Facets Dialog Box](view-facets-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="37318-117">For more information on the available options in this dialog box, see [View Facets Dialog Box](view-facets-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="37318-118">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="37318-118">When finished, click **OK**.</span></span>  
  
  
