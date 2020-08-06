---
title: Criar uma nova condição de gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policy conditions
ms.assetid: 8a612f7e-6c70-49db-a4de-48431e097cc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e4fe206c9a82b69101508f6f0a760ca9c1bc423d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574678"
---
# <a name="create-a-new-policy-based-management-condition"></a><span data-ttu-id="662c9-102">Criar uma nova condição de Gerenciamento baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="662c9-102">Create a New Policy-Based Management Condition</span></span>
  <span data-ttu-id="662c9-103">Este tópico descreve como criar uma condição de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="662c9-103">This topic describes how to create a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="662c9-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="662c9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="662c9-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="662c9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="662c9-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="662c9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="662c9-107">**Para criar uma condição, usando:**</span><span class="sxs-lookup"><span data-stu-id="662c9-107">**To create a condition, using:**</span></span>  
  
     [<span data-ttu-id="662c9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="662c9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="662c9-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="662c9-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="662c9-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="662c9-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="662c9-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="662c9-111">Permissions</span></span>  
 <span data-ttu-id="662c9-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="662c9-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="662c9-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="662c9-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-condition"></a><span data-ttu-id="662c9-114">Para criar uma condição</span><span class="sxs-lookup"><span data-stu-id="662c9-114">To create a condition</span></span>  
  
1.  <span data-ttu-id="662c9-115">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar uma condição de Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="662c9-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a Policy-based Management condition.</span></span>  
  
2.  <span data-ttu-id="662c9-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="662c9-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="662c9-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="662c9-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="662c9-118">Clique no sinal de adição para expandir a pasta **Facetas** .</span><span class="sxs-lookup"><span data-stu-id="662c9-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="662c9-119">Clique com o botão direito do mouse na faceta em que você deseja criar uma nova condição e selecione **Nova Condição**.</span><span class="sxs-lookup"><span data-stu-id="662c9-119">Right-click the facet in which you want to create a new condition and select **New Condition**.</span></span>  
  
6.  <span data-ttu-id="662c9-120">Na caixa de diálogo **Criar Nova Condição** , na caixa **Nome** , digite o nome da nova condição.</span><span class="sxs-lookup"><span data-stu-id="662c9-120">In the **Create New Condition** dialog box, in the **Name** box, type the name of the new condition.</span></span>  
  
7.  <span data-ttu-id="662c9-121">Confirme a faceta correta na lista **Faceta** ou selecione uma faceta diferente.</span><span class="sxs-lookup"><span data-stu-id="662c9-121">Confirm the correct facet in the **Facet** list, or select a different facet.</span></span>  
  
8.  <span data-ttu-id="662c9-122">Em **Expressão**, construa expressões de condição selecionando uma propriedade de faceta na caixa **Campo** , junto com o operador e o valor associados.</span><span class="sxs-lookup"><span data-stu-id="662c9-122">Under **Expression**, construct condition expressions by selecting a facet property in the **Field** box, together with its associated operator and value.</span></span> <span data-ttu-id="662c9-123">Quando você adicionar várias expressões, as expressões podem ser unidas usando **E** ou **Ou**.</span><span class="sxs-lookup"><span data-stu-id="662c9-123">When you add multiple expressions, the expressions can be joined by using **And** or **Or**.</span></span> <span data-ttu-id="662c9-124">Para obter mais informações sobre as opções disponíveis nesta caixa de diálogo, veja [Caixa de diálogo Criar Nova Condição ou Abrir Condição, Página Geral](../../integration-services/general-page-of-integration-services-designers-options.md), [Caixa de diálogo Criar Nova Condição ou Abrir Condição, Página de Descrição](create-new-condition-or-open-condition-dialog-box-description-page.md) e [Caixa de diálogo Edição Avançada &#40;Condição&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="662c9-124">For more information on the available options in this dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
9. <span data-ttu-id="662c9-125">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="662c9-125">When finished, click **OK**.</span></span>  
  
  
