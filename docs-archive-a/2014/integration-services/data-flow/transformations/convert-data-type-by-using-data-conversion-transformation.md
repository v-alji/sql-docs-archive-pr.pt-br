---
title: Converter dados em um tipo de dados diferente usando a transformação conversão de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: 4aabbe4f-7666-4672-865a-9627bd25fbfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 878741717c36c18e9a069c62e86be0148272239f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575244"
---
# <a name="convert-data-to-a-different-data-type-by-using-the-data-conversion-transformation"></a><span data-ttu-id="16230-102">Converter dados em um tipo de dados diferente por meio da transformação Conversão de Dados</span><span class="sxs-lookup"><span data-stu-id="16230-102">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>
  <span data-ttu-id="16230-103">Para adicionar e configurar uma transformação Conversão de Dados, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma fonte.</span><span class="sxs-lookup"><span data-stu-id="16230-103">To add and configure a Data Conversion transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-convert-data-to-a-different-data-type"></a><span data-ttu-id="16230-104">Para converte dados em um tipo de dados diferente</span><span class="sxs-lookup"><span data-stu-id="16230-104">To convert data to a different data type</span></span>  
  
1.  <span data-ttu-id="16230-105">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="16230-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="16230-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="16230-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="16230-107">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a transformação Conversão de Dados para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="16230-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Data Conversion transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="16230-108">Conecte a transformação Conversão de Dados ao fluxo de dados arrastando um conector de uma fonte ou transformação anterior para a transformação Conversão de Dados.</span><span class="sxs-lookup"><span data-stu-id="16230-108">Connect the Data Conversion transformation to the data flow by dragging a connector from the source or the previous transformation to the Data Conversion transformation.</span></span>  
  
5.  <span data-ttu-id="16230-109">Clique duas vezes na transformação Conversão de Dados.</span><span class="sxs-lookup"><span data-stu-id="16230-109">Double-click the Data Conversion transformation.</span></span>  
  
6.  <span data-ttu-id="16230-110">Na caixa de diálogo **Editor de Transformação Conversão de Dados** , na tabela **Colunas de Entrada Disponíveis** , marque a caixa de seleção ao lado das colunas das quais o tipo de dados você deseja converter.</span><span class="sxs-lookup"><span data-stu-id="16230-110">In the **Data ConversionTransformation Editor** dialog box, in the **Available Input Columns** table, select the check box next to the columns whose data type you want to convert.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16230-111">É possível aplicar diversas conversões de dados a uma coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="16230-111">You can apply multiple data conversions to an input column.</span></span>  
  
7.  <span data-ttu-id="16230-112">Como opção, modifique os valores padrão na coluna **Alias de Saída** .</span><span class="sxs-lookup"><span data-stu-id="16230-112">Optionally, modify the default values in the **Output Alias** column.</span></span>  
  
8.  <span data-ttu-id="16230-113">Na lista **Tipo de Dados** , selecione o novo tipo de dados para a coluna.</span><span class="sxs-lookup"><span data-stu-id="16230-113">In the **Data Type** list, select the new data type for the column.</span></span> <span data-ttu-id="16230-114">O tipo de dados padrão é o tipo de dados da coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="16230-114">The default data type is the data type of the input column.</span></span>  
  
9. <span data-ttu-id="16230-115">Como opção, dependendo do tipo de dados selecionado, atualize os valores nas colunas **Comprimento**, **Precisão**, **Escala**e **Página de Código** .</span><span class="sxs-lookup"><span data-stu-id="16230-115">Optionally, depending on the selected data type, update the values in the **Length**, the **Precision**, the **Scale**, and the **Code Page** columns.</span></span>  
  
10. <span data-ttu-id="16230-116">Para configurar a saída de erro, clique em **Configurar Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="16230-116">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="16230-117">Para obter mais informações, consulte [Configurar uma saída de erro em um componente de fluxo de dados](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="16230-117">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="16230-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="16230-118">Click **OK**.</span></span>  
  
12. <span data-ttu-id="16230-119">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="16230-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16230-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16230-120">See Also</span></span>  
 <span data-ttu-id="16230-121">[Data Conversion Transformation](data-conversion-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="16230-121">[Data Conversion Transformation](data-conversion-transformation.md) </span></span>  
 <span data-ttu-id="16230-122">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="16230-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="16230-123">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="16230-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="16230-124">[Tipos de dados do Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="16230-124">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 [<span data-ttu-id="16230-125">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="16230-125">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
