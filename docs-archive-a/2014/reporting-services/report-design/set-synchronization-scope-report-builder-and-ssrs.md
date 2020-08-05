---
title: Definir o escopo da sincronização (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6f4a11e6-6151-47be-a43f-e3dbf6c0e737
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3efbb7774d5116c9b3a18457291434f2a05aac7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569088"
---
# <a name="set-synchronization-scope-report-builder-and-ssrs"></a><span data-ttu-id="a5d70-102">Definir o escopo da sincronização (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a5d70-102">Set Synchronization Scope (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a5d70-103">Os indicadores transmitem valores de dados fazendo a sincronização do intervalo de valores de dados de indicador em um escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="a5d70-103">Indicators convey data values by synchronizing across the range of indicator values within a specified scope.</span></span> <span data-ttu-id="a5d70-104">Por padrão, o escopo é o contêiner pai do indicador, como a tabela ou matriz que contém o indicador.</span><span class="sxs-lookup"><span data-stu-id="a5d70-104">By default, the scope is the parent container of the indicator such as the table or matrix that contains the indicator.</span></span> <span data-ttu-id="a5d70-105">Você pode alterar a sincronização do indicador dependendo do layout do seu relatório.</span><span class="sxs-lookup"><span data-stu-id="a5d70-105">You can change the synchronization of the indicator depending on the layout of your report.</span></span> <span data-ttu-id="a5d70-106">Por exemplo, se uma região de dados, como uma tabela, tiver um grupo de linhas, você poderá especificar o grupo como o escopo de indicador.</span><span class="sxs-lookup"><span data-stu-id="a5d70-106">For example, if a data region such as a table has a row group, you can specify the group as the indicator scope.</span></span> <span data-ttu-id="a5d70-107">O indicador também pode omitir a sincronização.</span><span class="sxs-lookup"><span data-stu-id="a5d70-107">The indicator can also omit synchronization.</span></span>  
  
 <span data-ttu-id="a5d70-108">Opções como unidades de medida podem ser definidas usando expressões.</span><span class="sxs-lookup"><span data-stu-id="a5d70-108">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="a5d70-109">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a5d70-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a5d70-110">Para obter informações gerais sobre como entender e definir escopo em relatórios, consulte [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a5d70-110">For general information about understanding and setting scope within reports, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-synchronization-scope-of-an-indicator"></a><span data-ttu-id="a5d70-111">Para alterar o escopo da sincronização de um indicador</span><span class="sxs-lookup"><span data-stu-id="a5d70-111">To change the synchronization scope of an indicator</span></span>  
  
1.  <span data-ttu-id="a5d70-112">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="a5d70-112">Right click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="a5d70-113">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="a5d70-113">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="a5d70-114">Na lista **Escopo da sincronização** , clique no escopo que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="a5d70-114">In the **Synchronization scope** list, click the scope that you want to apply.</span></span>  
  
     <span data-ttu-id="a5d70-115">A opção **(Nenhum)** , que remove o escopo da sincronização do indicador, está sempre disponível.</span><span class="sxs-lookup"><span data-stu-id="a5d70-115">The **(None)** option, which removes synchronization scope from the indicator, is always available.</span></span> <span data-ttu-id="a5d70-116">Outras opções dependem do layout do relatório.</span><span class="sxs-lookup"><span data-stu-id="a5d70-116">Other options depend on the layout of your report.</span></span>  
  
     <span data-ttu-id="a5d70-117">Se desejar, clique no botão **Expressão** (*fx*) para editar uma expressão que define o escopo.</span><span class="sxs-lookup"><span data-stu-id="a5d70-117">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the scope.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5d70-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5d70-118">See Also</span></span>  
 [<span data-ttu-id="a5d70-119">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a5d70-119">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
