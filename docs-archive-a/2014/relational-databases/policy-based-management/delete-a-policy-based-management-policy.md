---
title: Excluir uma política do gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policies
ms.assetid: 488f0305-190c-4223-aa5c-e9bd43b520eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c43bc3cdf4a7a5b5d9268bbd7e68506616d1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678721"
---
# <a name="delete-a-policy-based-management-policy"></a><span data-ttu-id="66297-102">Excluir uma política do Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="66297-102">Delete a Policy-Based Management Policy</span></span>
  <span data-ttu-id="66297-103">Este tópico descreve como excluir uma Política de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66297-103">This topic describes how to delete a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="66297-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="66297-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="66297-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="66297-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="66297-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="66297-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="66297-107">**Para excluir uma política, usando:**</span><span class="sxs-lookup"><span data-stu-id="66297-107">**To delete a policy, using:**</span></span>  
  
     [<span data-ttu-id="66297-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66297-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="66297-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="66297-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="66297-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="66297-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="66297-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="66297-111">Permissions</span></span>  
 <span data-ttu-id="66297-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="66297-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="66297-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66297-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-policy"></a><span data-ttu-id="66297-114">Para excluir uma política</span><span class="sxs-lookup"><span data-stu-id="66297-114">To delete a policy</span></span>  
  
1.  <span data-ttu-id="66297-115">No Pesquisador de Objetos, clique no sinal de adição para expandir o servidor que contém a Política de Gerenciamento Baseado em Políticas que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="66297-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to delete.</span></span>  
  
2.  <span data-ttu-id="66297-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="66297-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="66297-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="66297-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="66297-118">Clique no sinal de adição para expandir a pasta **Políticas** .</span><span class="sxs-lookup"><span data-stu-id="66297-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="66297-119">Clique com o botão direito do mouse na política que deseja excluir e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="66297-119">Right-click the policy that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="66297-120">Na caixa de diálogo **Excluir Objeto** , verifique se a condição correta está selecionada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="66297-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
