---
title: Exibir as propriedades de uma faceta de gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea24ff2768ecaeec426a8689455912d848b54813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571981"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a><span data-ttu-id="32edb-102">Exibir as propriedades de uma faceta de gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="32edb-102">View the Properties of a Policy-Based Management Facet</span></span>
  <span data-ttu-id="32edb-103">Este tópico descreve como exibir as propriedades de uma faceta do Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32edb-103">This topic describes how to view the properties of a Policy-Based Management facet in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="32edb-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="32edb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="32edb-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="32edb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="32edb-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="32edb-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="32edb-107">**Para exibir as propriedades de uma faceta, usando:**</span><span class="sxs-lookup"><span data-stu-id="32edb-107">**To view the properties of a facet, using:**</span></span>  
  
     [<span data-ttu-id="32edb-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="32edb-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="32edb-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="32edb-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="32edb-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="32edb-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="32edb-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="32edb-111">Permissions</span></span>  
 <span data-ttu-id="32edb-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="32edb-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="32edb-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="32edb-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-facet"></a><span data-ttu-id="32edb-114">Para visualizar as propriedades de uma faceta</span><span class="sxs-lookup"><span data-stu-id="32edb-114">To view the properties of a facet</span></span>  
  
1.  <span data-ttu-id="32edb-115">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a faceta cujas propriedades você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="32edb-115">In **Object Explorer**, click the plus sign to expand the server that contains the facet whose properties you want to view.</span></span>  
  
2.  <span data-ttu-id="32edb-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="32edb-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="32edb-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="32edb-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="32edb-118">Clique no sinal de adição para expandir a pasta **Facetas** .</span><span class="sxs-lookup"><span data-stu-id="32edb-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="32edb-119">Clique com o botão direito do mouse na faceta cujas propriedades você deseja exibir e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="32edb-119">Right-click the facet whose properties you want to view and select **Properties**.</span></span> <span data-ttu-id="32edb-120">Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Propriedades da faceta -**_nome_da_faceta_, confira [Caixa de diálogo Propriedades de Faceta, página Geral](../../integration-services/general-page-of-integration-services-designers-options.md), [Caixa de diálogo Propriedades da Faceta, página Políticas Dependentes](facet-properties-dialog-box-dependent-policies-page.md) e [Caixa de diálogo Propriedades da Faceta, página Condições Dependentes](facet-properties-dialog-box-dependent-conditions-page.md).</span><span class="sxs-lookup"><span data-stu-id="32edb-120">For more information on the available options in the **Facet Properties -**_facet_name_ dialog box, see [Facet Properties Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Facet Properties Dialog Box, Dependent Policies Page](facet-properties-dialog-box-dependent-policies-page.md), and [Facet Properties Dialog Box, Dependent Conditions Page](facet-properties-dialog-box-dependent-conditions-page.md).</span></span>  
  
6.  <span data-ttu-id="32edb-121">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32edb-121">When finished, click **Close**.</span></span>  
  
  
