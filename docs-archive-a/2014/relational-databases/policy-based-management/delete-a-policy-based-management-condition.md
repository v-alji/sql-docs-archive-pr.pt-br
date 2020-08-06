---
title: Excluir uma condição de gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policy conditions
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02a5294ecb53db4d8baa4f3dae0a232d9551a13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569396"
---
# <a name="delete-a-policy-based-management-condition"></a><span data-ttu-id="7e29c-102">Excluir uma condição de Gerenciamento baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="7e29c-102">Delete a Policy-Based Management Condition</span></span>
  <span data-ttu-id="7e29c-103">Este tópico descreve como excluir uma condição de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e29c-103">This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="7e29c-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7e29c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e29c-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7e29c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e29c-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e29c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e29c-107">**Para excluir uma condição, usando:**</span><span class="sxs-lookup"><span data-stu-id="7e29c-107">**To delete a condition, using:**</span></span>  
  
     [<span data-ttu-id="7e29c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e29c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e29c-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7e29c-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e29c-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e29c-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e29c-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="7e29c-111">Permissions</span></span>  
 <span data-ttu-id="7e29c-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="7e29c-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e29c-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e29c-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-condition"></a><span data-ttu-id="7e29c-114">Para excluir uma condição</span><span class="sxs-lookup"><span data-stu-id="7e29c-114">To delete a condition</span></span>  
  
1.  <span data-ttu-id="7e29c-115">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a condição que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="7e29c-115">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.</span></span>  
  
2.  <span data-ttu-id="7e29c-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="7e29c-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="7e29c-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="7e29c-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="7e29c-118">Clique no sinal de adição para expandir a pasta **Condições** .</span><span class="sxs-lookup"><span data-stu-id="7e29c-118">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="7e29c-119">Clique com o botão direito do mouse na condição a ser excluída e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7e29c-119">Right-click the condition that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="7e29c-120">Na caixa de diálogo **Excluir Objeto** , verifique se a condição correta está selecionada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e29c-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
