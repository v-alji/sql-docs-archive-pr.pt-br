---
title: Adicionar um visualizador de dados a um fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data viewers [Integration Services]
- data flow [Integration Services], data viewers
- adding data viewers
ms.assetid: 5e573274-a170-4132-bfc8-a8ff3a8411e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7abd76417552ec50da736afe024a5ae36ee6a2ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569596"
---
# <a name="add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="31d76-102">Adicionar um visualizador de dados a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="31d76-102">Add a Data Viewer to a Data Flow</span></span>
  <span data-ttu-id="31d76-103">Este tópico descreve como adicionar e configurar um visualizador de dados em um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="31d76-103">This topic describes how to add and configure a data viewer in a data flow.</span></span> <span data-ttu-id="31d76-104">Um visualizador de dados exibe dados que estão se movendo entre dois componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="31d76-104">A data viewer displays data that is moving between two data flow components.</span></span> <span data-ttu-id="31d76-105">Por exemplo, um visualizador de dados pode exibir os dados extraídos de uma fonte antes de uma transformação no fluxo de dados modificar os dados.</span><span class="sxs-lookup"><span data-stu-id="31d76-105">For example, a data viewer can display the data that is extracted from a data source before a transformation in the data flow modifies the data.</span></span>  
  
 <span data-ttu-id="31d76-106">Um caminho conecta componentes em um fluxo de dados conectando a saída de um componente de fluxo de dados à entrada de outro componente.</span><span class="sxs-lookup"><span data-stu-id="31d76-106">A path connects components in a data flow by connecting the output of one data flow component to the input of another component.</span></span>  
  
 <span data-ttu-id="31d76-107">Antes de adicionar visualizadores de dados, um pacote deve incluir uma tarefa Fluxo de Dados e pelo menos dois componentes de fluxo de dados que estejam conectados.</span><span class="sxs-lookup"><span data-stu-id="31d76-107">Before you can add data viewers to a package, the package must include a Data Flow task and at least two data flow components that are connected.</span></span>  
  
### <a name="to-add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="31d76-108">Para adicionar um visualizador de dados a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="31d76-108">To add a data viewer to a data flow</span></span>  
  
1.  <span data-ttu-id="31d76-109">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="31d76-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="31d76-110">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="31d76-110">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="31d76-111">Clique na guia **Fluxo de Controle** , se ainda não estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="31d76-111">Click the **Control Flow** tab, if it is not already active.</span></span>  
  
4.  <span data-ttu-id="31d76-112">Clique na tarefa Fluxo de Dados do fluxo de dados ao qual você deseja conectar um visualizador de dados e, em seguida, clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="31d76-112">Click the Data Flow task to whose data flow you want to attach a data viewer and then click the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="31d76-113">Clique com o botão direito do mouse em um caminho entre dois componentes de fluxo de dados e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="31d76-113">Right-click a path between two data flow components, and click **Edit**.</span></span>  
  
6.  <span data-ttu-id="31d76-114">Na página **Geral** , você pode exibir e editar propriedades do caminho.</span><span class="sxs-lookup"><span data-stu-id="31d76-114">On the **General** page, you can view and edit path properties.</span></span> <span data-ttu-id="31d76-115">Por exemplo, na lista suspensa **PathAnnotation** , você pode selecionar a anotação que aparece ao lado do caminho.</span><span class="sxs-lookup"><span data-stu-id="31d76-115">For example, from the **PathAnnotation** drop-down list you can select the annotation that appears next to the path.</span></span>  
  
7.  <span data-ttu-id="31d76-116">Na página **Metadados** , você pode exibir os metadados da coluna e copiar os metadados na Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="31d76-116">On the **Metadata** page, you can view the column metadata and copy the metadata to the Clipboard.</span></span>  
  
8.  <span data-ttu-id="31d76-117">Na página **Visualizador de Dados** , clique em **Habilitar visualizador de dados**.</span><span class="sxs-lookup"><span data-stu-id="31d76-117">On the **Data Viewer** page, click **Enable data viewer**.</span></span>  
  
9. <span data-ttu-id="31d76-118">Na área Colunas para exibição, selecione as colunas a serem exibidas no visualizador de dados.</span><span class="sxs-lookup"><span data-stu-id="31d76-118">In the Columns to display area, select the columns you want to display in the data viewer.</span></span> <span data-ttu-id="31d76-119">Por padrão, todas as colunas disponíveis são selecionadas e relacionadas na lista **Colunas Exibidas** .</span><span class="sxs-lookup"><span data-stu-id="31d76-119">By default, all the available columns are selected and listed in the **Displayed Columns** list.</span></span> <span data-ttu-id="31d76-120">Mova as colunas que não deseja usar para a lista **Coluna Não Usada** selecionando-as e clicando na seta para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="31d76-120">Move columns that you do not want to use to the **Unused Column** list by selecting them and then clicking the left arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31d76-121">Na grade, os valores que representam os tipos de dados DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 e DT_DBTIMESTAMPOFFSET aparecem como cadeias de caracteres formatadas conforme o ISO 8601 e um separador de espaço substitui o separador `T`.</span><span class="sxs-lookup"><span data-stu-id="31d76-121">In the grid, values that represent the DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types appear as ISO 8601 formatted strings and a space separator replaces the `T` separator.</span></span> <span data-ttu-id="31d76-122">Os valores que representam os tipos de dados DT_DATE e DT_FILETIME incluem sete dígitos para os segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="31d76-122">Values that represent the DT_DATE and DT_FILETIME data types include seven digits for fractional seconds.</span></span> <span data-ttu-id="31d76-123">Como o tipo de dados DT_FILETIME armazena somente três dígitos de segundos fracionários, a grade exibe zeros nos quatro dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="31d76-123">Because the DT_FILETIME data type stores only three digits of fractional seconds, the grid displays zeros for the remaining four digits.</span></span> <span data-ttu-id="31d76-124">Os valores que representam o tipo de dados DT_DBTIMESTAMP incluem três dígitos para os segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="31d76-124">Values that represent the DT_DBTIMESTAMP data type include three digits for fractional seconds.</span></span> <span data-ttu-id="31d76-125">Para os valores que representam os tipos de dados DT_DBTIME2, DT_DBTIMESTAMP2 e DT_DBTIMESTAMPOFFSET, o número de dígitos para os segundos fracionários corresponde à escala especificada para o tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="31d76-125">For values that represent the DT_DBTIME2, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types, the number of digits for fractional seconds corresponds to the scale specified for the column's data type.</span></span> <span data-ttu-id="31d76-126">Para obter mais informações sobre os formatos ISO 8601, consulte [Formatos de data e hora](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="31d76-126">For more information about ISO 8601 formats, see [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span> <span data-ttu-id="31d76-127">Para obter mais informações sobre tipos de dados, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="31d76-127">For more information about data types, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
10. <span data-ttu-id="31d76-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="31d76-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d76-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31d76-129">See Also</span></span>  
 <span data-ttu-id="31d76-130">[Transformações do Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="31d76-130">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="31d76-131">[Caminhos do Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="31d76-131">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="31d76-132">[Fluxo de Dados](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="31d76-132">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="31d76-133">Depurar o fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="31d76-133">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
  
