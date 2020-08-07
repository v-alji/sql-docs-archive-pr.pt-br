---
title: Publicar dados do Excel para o MDS (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 597a954760816d8938628974998fe8f6daad1af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581981"
---
# <a name="publish-data-from-excel-to-mds-mds-add-in-for-excel"></a><span data-ttu-id="54578-102">Publicar dados do Excel no MDS (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="54578-102">Publish Data from Excel to MDS (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="54578-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publique dados no repositório do MDS quando terminar seu trabalho no Excel e desejar salvar as alterações para que outros usuários tenham acesso a elas.</span><span class="sxs-lookup"><span data-stu-id="54578-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you are finished working in Excel and want to save your changes so other users have access to them.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="54578-104">Quando você publicar alterações, os comentários das células gerenciadas pelo MDS serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="54578-104">When you publish changes, comments on MDS-managed cells are deleted.</span></span>  
> -   <span data-ttu-id="54578-105">Uma fórmula não tem suporte em uma célula gerenciada por MDS.</span><span class="sxs-lookup"><span data-stu-id="54578-105">A formula is not supported in an MDS-managed cell.</span></span> <span data-ttu-id="54578-106">Uma fórmula em uma célula gerenciada por MDS é tratada como um valor de texto.</span><span class="sxs-lookup"><span data-stu-id="54578-106">A formula in an MDS-managed cell is handled as a text value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54578-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="54578-107">Prerequisites</span></span>  
 <span data-ttu-id="54578-108">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="54578-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="54578-109">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="54578-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="54578-110">A planilha ativa deve conter dados gerenciados no MDS e você deve ter feito alterações ou adições aos dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="54578-110">The active worksheet must contain MDS-managed data and you must have made changes or additions to the MDS-managed data.</span></span>  
  
-   <span data-ttu-id="54578-111">Se você for adicionar membros, não precisará especificar um valor de **Código** se os códigos da entidade forem gerados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="54578-111">If you are adding members, you do not have to specify a **Code** value if codes for the entity are being automatically generated.</span></span> <span data-ttu-id="54578-112">Para obter mais informações, consulte [criação automática de código &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="54578-112">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span></span>  
  
### <a name="to-publish-data-to-the-mds-repository"></a><span data-ttu-id="54578-113">Para publicar dados no repositório do MDS</span><span class="sxs-lookup"><span data-stu-id="54578-113">To publish data to the MDS repository</span></span>  
  
1.  <span data-ttu-id="54578-114">No grupo **Publicar e Validar** , clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="54578-114">In the **Publish and Validate** group, click **Publish**.</span></span>  
  
2.  <span data-ttu-id="54578-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="54578-115">Optional.</span></span> <span data-ttu-id="54578-116">Se a caixa de diálogo **Publicar e Anotar** for exibida, opte por compartilhar a mesma anotação (comentário) para todas as atualizações, ou por anotar cada alteração individualmente.</span><span class="sxs-lookup"><span data-stu-id="54578-116">If the **Publish and Annotate** dialog box is displayed, choose to share the same annotation (comment) for all updates, or to annotate each change individually.</span></span>  
  
3.  <span data-ttu-id="54578-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="54578-117">Optional.</span></span> <span data-ttu-id="54578-118">Selecione a caixa de seleção **Não mostrar esta caixa de diálogo novamente** .</span><span class="sxs-lookup"><span data-stu-id="54578-118">Select the **Do not show this dialog box again** check box.</span></span> <span data-ttu-id="54578-119">Você sempre pode mostrar a caixa de diálogo no futuro escolhendo **Configurações** e marcando a caixa de seleção **Mostrar a caixa de diálogo Publicar e Anotar ao publicar** .</span><span class="sxs-lookup"><span data-stu-id="54578-119">You can always show the dialog box in the future by choosing **Settings** and selecting the **Show Publish and Annotate dialog box when publishing** check box.</span></span>  
  
4.  <span data-ttu-id="54578-120">Clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="54578-120">Click **Publish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54578-121">Se você for adicionar novos membros (linhas) à sua planilha e não conseguir publicá-los com êxito no repositório do MDS, talvez você não tenha a permissão **Atualizar** para todos os atributos da planilha.</span><span class="sxs-lookup"><span data-stu-id="54578-121">If you are adding new members (rows) to your worksheet and you cannot successfully publish them to the MDS repository, you may not have **Update** permission to all of the attributes in the worksheet.</span></span> <span data-ttu-id="54578-122">Na guia **Revisão** , no grupo **Alterações** , clique em **Desproteger Planilha** e tente publicar novamente.</span><span class="sxs-lookup"><span data-stu-id="54578-122">On the **Review** tab, in the **Changes** group, click **Unprotect Sheet** and try to publish again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="54578-123">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="54578-123">Next Steps</span></span>  
 [<span data-ttu-id="54578-124">Aplicar regras de negócio &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="54578-124">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="54578-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54578-125">See Also</span></span>  
 <span data-ttu-id="54578-126">[Publicando dados &#40;Suplemento MDS para Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="54578-126">[Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="54578-127">Validando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="54578-127">Validating Data &#40;MDS Add-in for Excel&#41;</span></span>](validating-data-mds-add-in-for-excel.md)  
  
  
