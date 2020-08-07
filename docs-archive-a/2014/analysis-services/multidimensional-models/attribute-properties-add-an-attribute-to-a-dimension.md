---
title: Adicionar um atributo a uma dimensão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583202"
---
# <a name="add-an--attribute-to-a-dimension"></a><span data-ttu-id="72452-102">Adicionar um atributo a uma dimensão</span><span class="sxs-lookup"><span data-stu-id="72452-102">Add an  Attribute to a Dimension</span></span>
  <span data-ttu-id="72452-103">Você pode adicionar um atributo a uma dimensão automaticamente ou manualmente no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72452-103">You can add an attribute to a dimension either automatically or manually in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="72452-104">Para criar um atributo automaticamente, na guia **Estrutura da Dimensão** , do Designer de Dimensão do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], selecione a coluna que você deseja mapear para um atributo e a arraste do painel **Exibição da Fonte de Dados** para o painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="72452-104">To create an attribute automatically, on the **Dimension Structure** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the column that you want to map to an attribute, and then drag that column from the **Data Source View** pane to the **Attributes** pane.</span></span> <span data-ttu-id="72452-105">Essa ação criará um atributo mapeado para a coluna e atribuirá a ele o mesmo nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="72452-105">This creates an attribute that is mapped to the column, and assigns the same name to the attribute as the name of the column.</span></span> <span data-ttu-id="72452-106">Se já houver um atributo com esse nome, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adicionará um número ordinal como sufixo, começando com "1" para o primeiro nome duplicado.</span><span class="sxs-lookup"><span data-stu-id="72452-106">If an attribute that uses that name already exists, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adds an ordinal number suffix, starting with "1" for the first duplicate name.</span></span>  
  
 <span data-ttu-id="72452-107">Para criar um atributo manualmente, configure o painel **Atributos** para exibição de grade.</span><span class="sxs-lookup"><span data-stu-id="72452-107">To create an attribute manually, set the **Attributes** pane to grid view.</span></span> <span data-ttu-id="72452-108">Na coluna nome da última linha da grade, clique no **\<new attribute>** Item.</span><span class="sxs-lookup"><span data-stu-id="72452-108">In the name column of the last row in the grid, click the **\<new attribute>** item.</span></span> <span data-ttu-id="72452-109">Digite um nome para o novo atributo.</span><span class="sxs-lookup"><span data-stu-id="72452-109">Type a name for the new attribute.</span></span> <span data-ttu-id="72452-110">Será criado um atributo que não será mapeado para uma coluna e que manterá as configurações padrão para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="72452-110">This creates an attribute that is not mapped to a column and that has default settings for all its properties.</span></span> <span data-ttu-id="72452-111">É possível definir o mapeamento na janela **Propriedades** do [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] configurando a propriedade **KeyColumns** do novo atributo.</span><span class="sxs-lookup"><span data-stu-id="72452-111">You can set the mapping in the **Properties** window of [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] by configuring the **KeyColumns** property for the new attribute.</span></span>  
  
 <span data-ttu-id="72452-112">Para obter mais informações, consulte [Definir um novo atributo automaticamente](attribute-properties-define-a-new-attribute-automatically.md), [Definir um novo atributo manualmente](../define-a-new-attribute-manually.md), [Associar um atributo a uma coluna de nome](attribute-properties-bind-an-attribute-to-a-name-column.md)e [Modificar a propriedade KeyColumn de um atributo](attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="72452-112">For more information, see [Define a New Attribute Automatically](attribute-properties-define-a-new-attribute-automatically.md), [Define a New Attribute Manually](../define-a-new-attribute-manually.md), [Bind an Attribute to a Name Column](attribute-properties-bind-an-attribute-to-a-name-column.md), and [Modify the KeyColumn Property of an Attribute](attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72452-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72452-113">See Also</span></span>  
 [<span data-ttu-id="72452-114">Referência de propriedades de atributo de dimensão</span><span class="sxs-lookup"><span data-stu-id="72452-114">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
