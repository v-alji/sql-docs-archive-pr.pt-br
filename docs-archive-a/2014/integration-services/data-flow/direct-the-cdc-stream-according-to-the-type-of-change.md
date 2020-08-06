---
title: Direcionar o fluxo de CDC de acordo com o tipo de alteração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a9b4e0c6a196669e4cedafcecf0477b228f3001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571495"
---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="f85f4-102">Direcionar o fluxo de CDC de acordo com o tipo de alteração</span><span class="sxs-lookup"><span data-stu-id="f85f4-102">Direct the CDC Stream According to the Type of Change</span></span>
  <span data-ttu-id="f85f4-103">Para adicionar e configurar uma Transformação de separador de CDC, o pacote deverá conter pelo menos uma tarefa de Fluxo de Dados e uma origem CDC.</span><span class="sxs-lookup"><span data-stu-id="f85f4-103">To add and configure a CDC splitter Transformation, the package must contain at least one Data Flow task and a CDC source.</span></span>  
  
 <span data-ttu-id="f85f4-104">A origem CDC adicionada ao pacote deve ter um modo de processamento NetCDC selecionado.</span><span class="sxs-lookup"><span data-stu-id="f85f4-104">The CDC source added to the package must have a NetCDC processing mode selected.</span></span> <span data-ttu-id="f85f4-105">Para obter mais informações sobre como selecionar modos de processamento, consulte [Editor de Origem CDC &#40;página Gerenciador de Conexões&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="f85f4-105">For more information on selecting processing modes, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="f85f4-106">Para direcionar o fluxo de CDC de acordo com o tipo de alteração</span><span class="sxs-lookup"><span data-stu-id="f85f4-106">To direct the CDC stream according to the type of change</span></span>  
  
1.  <span data-ttu-id="f85f4-107">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra o projeto do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="f85f4-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f85f4-108">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="f85f4-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f85f4-109">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste o separador de CDC para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="f85f4-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC splitter to the design surface.</span></span>  
  
4.  <span data-ttu-id="f85f4-110">Conecte a origem CDC que é incluída no pacote ao Separador de CDC.</span><span class="sxs-lookup"><span data-stu-id="f85f4-110">Connect the CDC source that is included in the package to the CDC Splitter.</span></span>  
  
5.  <span data-ttu-id="f85f4-111">Conecte o separador de CDC a um ou mais destinos.</span><span class="sxs-lookup"><span data-stu-id="f85f4-111">Connect the CDC splitter to one or more destinations.</span></span> <span data-ttu-id="f85f4-112">Você pode conectar até três saídas diferentes.</span><span class="sxs-lookup"><span data-stu-id="f85f4-112">You can connect up to three different outputs.</span></span>  
  
6.  <span data-ttu-id="f85f4-113">Selecione uma das saídas a seguir:</span><span class="sxs-lookup"><span data-stu-id="f85f4-113">Select one of the following outputs:</span></span>  
  
    -   <span data-ttu-id="f85f4-114">Excluir saída: a saída para onde as linhas de alteração DELETE são direcionadas.</span><span class="sxs-lookup"><span data-stu-id="f85f4-114">Delete output: The output where DELETE change rows are directed.</span></span>  
  
    -   <span data-ttu-id="f85f4-115">Inserir saída: a saída para onde as linhas de alteração INSERT são direcionadas.</span><span class="sxs-lookup"><span data-stu-id="f85f4-115">Insert output: The output where INSERT change rows are directed.</span></span>  
  
    -   <span data-ttu-id="f85f4-116">Saída de atualização: a saída para onde as linhas de alteração UPDATE antes/depois e as linhas de alteração Mesclar são direcionadas.</span><span class="sxs-lookup"><span data-stu-id="f85f4-116">Update output: The output where before/after UPDATE change rows and Merge change rows are directed.</span></span>  
  
7.  <span data-ttu-id="f85f4-117">Opcionalmente, você pode configurar as propriedades avançadas usando a caixa de diálogo **Editor Avançado** .</span><span class="sxs-lookup"><span data-stu-id="f85f4-117">Optionally, you can configure the advanced properties using the **Advanced Editor** dialog box.</span></span>  
  
     <span data-ttu-id="f85f4-118">A caixa de diálogo **Editor Avançado** contém as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="f85f4-118">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
     <span data-ttu-id="f85f4-119">Para abrir a caixa de diálogo **Editor Avançado** :</span><span class="sxs-lookup"><span data-stu-id="f85f4-119">To open the **Advanced Editor** dialog box:</span></span>  
  
    -   <span data-ttu-id="f85f4-120">Na tela **Fluxo de Dados** do seu projeto do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , clique com o botão direito do mouse no separador de CDC e selecione **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="f85f4-120">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
     <span data-ttu-id="f85f4-121">Para obter mais informações sobre como usar o separador de CDC, consulte Componentes de CDC para Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="f85f4-121">For more information about using the CDC splitter see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85f4-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f85f4-122">See Also</span></span>  
 [<span data-ttu-id="f85f4-123">Divisor de CDC</span><span class="sxs-lookup"><span data-stu-id="f85f4-123">CDC Splitter</span></span>](cdc-splitter.md)  
  
  
