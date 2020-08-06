---
title: Caixa de diálogo modelo de nomeação de nível (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dd704e619e49f0dd1adb8fed8f1e743b61309af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686433"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="75f2b-102">Caixa de diálogo Modelo de Nomeação de Nível (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="75f2b-102">Level Naming Template Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="75f2b-103">Use a caixa de diálogo **Modelo de Nomeação de Nível** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para construir o modelo de nomeação de nível para um atributo pai em uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="75f2b-103">Use the **Level Naming Template** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to construct the level naming template for a parent attribute in a dimension.</span></span> <span data-ttu-id="75f2b-104">Para obter mais informações sobre modelos de nomeação de nível, consulte [Elemento NamingTemplate &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span><span class="sxs-lookup"><span data-stu-id="75f2b-104">For more information about level naming templates, see [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span></span> <span data-ttu-id="75f2b-105">Você pode exibir a caixa de diálogo **modelo de nomeação de nível** clicando no botão de reticências (**...**) no `NamingTemplate` valor de uma tradução para um atributo no painel **detalhes da conversão** na guia **traduções** do **Designer de dimensão**.</span><span class="sxs-lookup"><span data-stu-id="75f2b-105">You can display the **Level Naming Template** dialog box by clicking the ellipsis button (**...**) on the `NamingTemplate` value of a translation for an attribute in the **Translation Details** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="75f2b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="75f2b-106">Options</span></span>  
  
|<span data-ttu-id="75f2b-107">Termo</span><span class="sxs-lookup"><span data-stu-id="75f2b-107">Term</span></span>|<span data-ttu-id="75f2b-108">Definição</span><span class="sxs-lookup"><span data-stu-id="75f2b-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="75f2b-109">**Definir o modelo de nível**</span><span class="sxs-lookup"><span data-stu-id="75f2b-109">**Define the level template**</span></span>|<span data-ttu-id="75f2b-110">Exibe uma grade na qual é possível projetar a hierarquia de níveis no atributo pai.</span><span class="sxs-lookup"><span data-stu-id="75f2b-110">Displays a grid in which you can design the hierarchy of levels in the parent attribute.</span></span> <span data-ttu-id="75f2b-111">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="75f2b-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="75f2b-112">**Nível**: exibe a posição ordinal do nível para o qual o nome especificado em **nome** é usado.</span><span class="sxs-lookup"><span data-stu-id="75f2b-112">**Level**: Displays the ordinal position of the level for which the name specified in **Name** is used.</span></span> <span data-ttu-id="75f2b-113">Para adicionar um novo modelo de nomeação para um nível, selecione **Nome** na linha que contém um asterisco (\*) em **Nível**.</span><span class="sxs-lookup"><span data-stu-id="75f2b-113">To add a new naming template for a level, select **Name** on the row that contains an asterisk (\*) in **Level**.</span></span><br /><br /> <span data-ttu-id="75f2b-114">**Nome**: contém o modelo de nomenclatura usado para o nível indicado em **nível**.</span><span class="sxs-lookup"><span data-stu-id="75f2b-114">**Name**: Contains the naming template used for the level indicated in **Level**.</span></span> <span data-ttu-id="75f2b-115">Para adicionar um espaço reservado para a posição ordinal do nível no modelo de nomeação, adicione um único asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="75f2b-115">To add a placeholder for the level ordinal position in the naming template, add a single asterisk (\*).</span></span> <span data-ttu-id="75f2b-116">Para adicionar um asterisco como parte do nome criado pelo modelo de nomeação, adicione dois asteriscos ( \* \* ).</span><span class="sxs-lookup"><span data-stu-id="75f2b-116">To add an asterisk as part of the name created by the naming template, add two asterisks (\*\*).</span></span>|  
|<span data-ttu-id="75f2b-117">**Apagar tudo**</span><span class="sxs-lookup"><span data-stu-id="75f2b-117">**Clear All**</span></span>|<span data-ttu-id="75f2b-118">Selecione para remover todas as linhas em **Definir o modelo de nível**.</span><span class="sxs-lookup"><span data-stu-id="75f2b-118">Select to remove all rows in **Define the level template**.</span></span>|  
|<span data-ttu-id="75f2b-119">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="75f2b-119">**Result**</span></span>|<span data-ttu-id="75f2b-120">Exibe o modelo de nomeação de nível construído pela caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="75f2b-120">Displays the level naming template constructed by the dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75f2b-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="75f2b-121">See Also</span></span>  
 <span data-ttu-id="75f2b-122">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="75f2b-122">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="75f2b-123">Traduções &#40;o designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="75f2b-123">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
