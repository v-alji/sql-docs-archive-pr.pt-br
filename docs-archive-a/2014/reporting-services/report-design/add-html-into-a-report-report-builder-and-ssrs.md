---
title: Adicionar HTML a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 30bd631a-f774-48e7-a13a-b6c2eb54d9bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 605c84843d62fb664a8a665a3fc3b024f8f87186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684073"
---
# <a name="add-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="1974a-102">Adicionar um HTML a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1974a-102">Add HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1974a-103">Usando um espaço reservado, você pode importar HTML de um campo em seu conjunto de dados para usar no relatório.</span><span class="sxs-lookup"><span data-stu-id="1974a-103">Using a placeholder, you can import HTML from a field in your dataset for use in the report.</span></span> <span data-ttu-id="1974a-104">Por padrão, um espaço reservado representa texto sem-formatação, portanto você precisará alterar o tipo de marcação do espaço reservado para HTML.</span><span class="sxs-lookup"><span data-stu-id="1974a-104">By default, a placeholder represents plain text, so you will need to change the placeholder mark-up type to HTML.</span></span> <span data-ttu-id="1974a-105">Para obter mais informações, consulte [Importando HTML para um relatório &#40;Construtor de Relatórios e SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1974a-105">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-html-from-a-field-in-your-dataset-into-a-text-box"></a><span data-ttu-id="1974a-106">Para adicionar HTML de um campo em seu conjunto de dados a uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="1974a-106">To add HTML from a field in your dataset into a text box</span></span>  
  
1.  <span data-ttu-id="1974a-107">Na guia **Inserir** , clique em **Lista**.</span><span class="sxs-lookup"><span data-stu-id="1974a-107">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="1974a-108">Clique na superfície de design e arraste-a para criar uma caixa com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="1974a-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
     <span data-ttu-id="1974a-109">A caixa de diálogo **Propriedades do Conjunto de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="1974a-109">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="1974a-110">Você pode usar um conjunto de dados compartilhado ou um conjunto de dados inserido em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="1974a-110">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="1974a-111">Para obter mais informações, clique em [Caixa de diálogo Propriedades do Conjunto de Dados, Consulta &#40;Construtor de Relatórios&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) ou [Caixa de diálogo Propriedades do Conjunto de Dados, Consulta](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="1974a-111">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="1974a-112">Na guia **Inserir** , clique em **Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="1974a-112">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="1974a-113">Clique na lista e arraste-a para criar uma caixa com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="1974a-113">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="1974a-114">Arraste um campo HTML do conjunto de dados para a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="1974a-114">Drag an HTML field from your dataset into the text box.</span></span> <span data-ttu-id="1974a-115">Será criado um espaço reservado para seu campo.</span><span class="sxs-lookup"><span data-stu-id="1974a-115">A placeholder is created for your field.</span></span>  
  
4.  <span data-ttu-id="1974a-116">Clique com o botão direito do mouse no espaço reservado e depois em **Propriedades do Espaço Reservado**.</span><span class="sxs-lookup"><span data-stu-id="1974a-116">Right-click the placeholder, and then click **Placeholder Properties**.</span></span>  
  
5.  <span data-ttu-id="1974a-117">Na guia **Geral** , verifique se a caixa **Valor** contém uma expressão que avalie para o campo descartado na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="1974a-117">On the **General** tab, verify that the **Value** box contains an expression that evaluates to the field you dropped in step 3.</span></span>  
  
6.  <span data-ttu-id="1974a-118">Clique em **HTML – Interpretar marcas HTML como estilos**.</span><span class="sxs-lookup"><span data-stu-id="1974a-118">Click **HTML - Interpret HTML tags as styles**.</span></span> <span data-ttu-id="1974a-119">Isso faz com que o campo seja avaliado como HTML.</span><span class="sxs-lookup"><span data-stu-id="1974a-119">This causes the field to be evaluated as HTML.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1974a-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1974a-120">See Also</span></span>  
 <span data-ttu-id="1974a-121">[Formatando números e datas &#40;Construtor de Relatórios e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1974a-121">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1974a-122">[Formatando linhas, cores e imagens &#40;Construtor de Relatórios e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1974a-122">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1974a-123">Caixa de diálogo Propriedades do Espaço Reservado, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1974a-123">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
