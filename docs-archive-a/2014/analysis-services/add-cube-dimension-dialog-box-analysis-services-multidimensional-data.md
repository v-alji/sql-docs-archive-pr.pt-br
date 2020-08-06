---
title: Caixa de diálogo Adicionar dimensão do cubo (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.addcubedimensiondialog.f1
helpviewer_keywords:
- Add Cube Dimension dialog box
ms.assetid: 625a3b1f-183b-445f-9bb7-96945c324767
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0de75c02c39b0690184f35f2b0b6a07d7ed9a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570347"
---
# <a name="add-cube-dimension-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d36c5-102">Caixa de diálogo Adicionar Dimensão do Cubo (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="d36c5-102">Add Cube Dimension Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d36c5-103">Use a caixa de diálogo **Adicionar Dimensão do Cubo** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para adicionar uma referência a uma dimensão de banco de dados em um cubo.</span><span class="sxs-lookup"><span data-stu-id="d36c5-103">Use the **Add Cube Dimension** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to add a reference to a database dimension to a cube.</span></span> <span data-ttu-id="d36c5-104">Você pode exibir a caixa de diálogo **Adicionar Dimensão do Cubo** procedendo de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="d36c5-104">You can display the **Add Cube Dimension** dialog box by doing one of the following:</span></span>  
  
-   <span data-ttu-id="d36c5-105">Clique em **Adicionar Dimensão do Cubo** no painel **Barra de Ferramentas** na guia **Estrutura do Cubo** ou **Uso da Dimensão** no Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="d36c5-105">Click **Add Cube Dimension** in the **Toolbar** pane on the **Cube Structure** or **Dimension Usage** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="d36c5-106">Clique com o botão direito do mouse no painel **Dimensões** na guia **Estrutura do Cubo** no Designer de Cubo e selecione **Adicionar Dimensão do Cubo** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="d36c5-106">Right-click the **Dimensions** pane on the **Cube Structure** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
-   <span data-ttu-id="d36c5-107">Clique com o botão direito do mouse no painel **Grade** na guia **Uso da Dimensão** no Designer de Cubo e selecione **Adicionar Dimensão do Cubo** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="d36c5-107">Right-click the **Grid** pane on the **Dimension Usage** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d36c5-108">Cada dimensão de cubo pode ter apenas uma relação com um grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d36c5-108">Each cube dimension can have only one relationship to a measure group.</span></span> <span data-ttu-id="d36c5-109">No entanto é possível criar mais de uma dimensão de cubo e adicioná-la ao cubo, se a dimensão do banco de dados no qual a dimensão do cubo é baseada estiver relacionada a grupos de medidas através de mais de uma relação na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d36c5-109">However, you can create more than one cube dimension and add it to the cube, if the database dimension on which the cube dimension is based is related to measure groups through more than one relationship in the data source view.</span></span> <span data-ttu-id="d36c5-110">Essas dimensões são referenciadas como dimensões com função múltipla e normalmente ocorrem com dimensões de tempo.</span><span class="sxs-lookup"><span data-stu-id="d36c5-110">Such dimensions are referred to as role-playing dimensions and commonly occur with time dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d36c5-111">Opções</span><span class="sxs-lookup"><span data-stu-id="d36c5-111">Options</span></span>  
 <span data-ttu-id="d36c5-112">**Selecionar dimensão**</span><span class="sxs-lookup"><span data-stu-id="d36c5-112">**Select dimension**</span></span>  
 <span data-ttu-id="d36c5-113">Selecione uma dimensão de banco de dados existente para adicionar uma dimensão de cubo baseada nessa dimensão ao cubo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d36c5-113">Select an existing database dimension to add a cube dimension based on it to the selected cube.</span></span> <span data-ttu-id="d36c5-114">Várias dimensões de cubo podem ser definidas a partir da mesma dimensão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d36c5-114">Multiple cube dimensions can be defined from the same database dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d36c5-115">Se mais de uma dimensão de cubo baseadas na mesma dimensão de banco de dados forem adicionadas a um cubo, as dimensões de cubo adicionais serão chamadas de dimensões com função múltipla.</span><span class="sxs-lookup"><span data-stu-id="d36c5-115">If more than one cube dimension based on the same database dimension is added to a cube, the additional cube dimensions are called role-playing dimensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36c5-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d36c5-116">See Also</span></span>  
 [<span data-ttu-id="d36c5-117">Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="d36c5-117">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
