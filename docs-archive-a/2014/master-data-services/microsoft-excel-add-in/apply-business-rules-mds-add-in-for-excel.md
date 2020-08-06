---
title: Aplicar regras de negócio (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cd106345-f561-4966-88d3-a69139b2bd78
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aad5ce6bcebb635fa4659c32654d67406d4ba0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680018"
---
# <a name="apply-business-rules-mds-add-in-for-excel"></a><span data-ttu-id="dee26-102">Aplicar regras de negócio (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="dee26-102">Apply Business Rules (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="dee26-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , aplique regras de negócio quando desejar validar dados e confirmar se eles são válidos.</span><span class="sxs-lookup"><span data-stu-id="dee26-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] apply business rules when you want to validate data and confirm that it is valid.</span></span> <span data-ttu-id="dee26-104">Você pode corrigir as validações e republicar os dados.</span><span class="sxs-lookup"><span data-stu-id="dee26-104">You can correct validations and re-publish the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dee26-105">A validação dos dados ocorre automaticamente quando você os publica.</span><span class="sxs-lookup"><span data-stu-id="dee26-105">Data validation occurs automatically when you publish data.</span></span> <span data-ttu-id="dee26-106">Para obter mais informações, consulte [Procedimento armazenado de validação &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dee26-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dee26-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="dee26-107">Prerequisites</span></span>  
 <span data-ttu-id="dee26-108">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="dee26-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dee26-109">Você deve ter acesso à área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="dee26-109">You must have access to the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="dee26-110">Você deve ter uma planilha ativa que contenha dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="dee26-110">You must have an active worksheet that contains MDS-managed data.</span></span>  
  
### <a name="to-apply-business-rules"></a><span data-ttu-id="dee26-111">Para aplicar regras de negócio</span><span class="sxs-lookup"><span data-stu-id="dee26-111">To apply business rules</span></span>  
  
1.  <span data-ttu-id="dee26-112">No grupo **Publicar e Validar** , clique em **Aplicar Regras**.</span><span class="sxs-lookup"><span data-stu-id="dee26-112">In the **Publish and Validate** group, click **Apply Rules**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dee26-113">O número de membros (linhas) que são validados de uma vez depende de uma configuração no [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dee26-113">The number of members (rows) that are validated at one time depends on a setting in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="dee26-114">Para obter mais informações, consulte [Configurações de regras de negócio](../system-settings-master-data-services.md#BusinessRules).</span><span class="sxs-lookup"><span data-stu-id="dee26-114">For more information, see [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span></span>  
  
2.  <span data-ttu-id="dee26-115">Os dados são validados em relação às regras de negócio e duas colunas de status são exibidas.</span><span class="sxs-lookup"><span data-stu-id="dee26-115">The data is validated against business rules and two status columns are displayed.</span></span> <span data-ttu-id="dee26-116">Se essas colunas não forem exibidas automaticamente, no grupo **Publicar e Validar** , clique em **Mostrar Status** para exibi-las.</span><span class="sxs-lookup"><span data-stu-id="dee26-116">If these columns are not displayed automatically, in the **Publish and Validate** group, click **Show Status** to view them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee26-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dee26-117">See Also</span></span>  
 [<span data-ttu-id="dee26-118">Publicando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="dee26-118">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
