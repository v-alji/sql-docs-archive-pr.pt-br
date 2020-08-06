---
title: Extrair dados usando a origem XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], XML
- XML source [Integration Services]
ms.assetid: 5d5be54c-2b7e-4957-9193-c5ea5c5d6d15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57758353c476badfba4cb12a1ef6b5101f16735d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685860"
---
# <a name="extract-data-by-using-the-xml-source"></a><span data-ttu-id="0a054-102">Extrair dados por meio da origem XML</span><span class="sxs-lookup"><span data-stu-id="0a054-102">Extract Data by Using the XML Source</span></span>
  <span data-ttu-id="0a054-103">Para adicionar e configurar uma origem XML, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="0a054-103">To add and configure an XML source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-xml-source"></a><span data-ttu-id="0a054-104">Para extrair dados usando uma origem XML</span><span class="sxs-lookup"><span data-stu-id="0a054-104">To extract data using an XML source</span></span>  
  
1.  <span data-ttu-id="0a054-105">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="0a054-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0a054-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="0a054-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0a054-107">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a origem XML para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="0a054-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the XML source to the design surface.</span></span>  
  
4.  <span data-ttu-id="0a054-108">Clique duas vezes na origem XML.</span><span class="sxs-lookup"><span data-stu-id="0a054-108">Double-click the XML source.</span></span>  
  
5.  <span data-ttu-id="0a054-109">No **Editor de Origem XML**, na página **Gerenciador de Conexões** , selecione um modo de acesso a dados:</span><span class="sxs-lookup"><span data-stu-id="0a054-109">In the **XML Source Editor**, on the **Connection Manager** page, select a data access mode:</span></span>  
  
    -   <span data-ttu-id="0a054-110">Para o modo de acesso **Local de arquivo XML** , clique em **Procurar** e localize a pasta que contém o arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="0a054-110">For the **XML file location** access mode, click **Browse** and locate the folder that contains the XML file.</span></span>  
  
    -   <span data-ttu-id="0a054-111">Para o modo de acesso **Arquivo XML de variável** , selecione a variável definida pelo usuário que contém o caminho do arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="0a054-111">For the **XML file from variable** access mode, select the user-defined variable that contains the path of the XML file.</span></span>  
  
    -   <span data-ttu-id="0a054-112">Para o modo de acesso **Dados XML de variável** , selecione a variável definida pelo usuário que contém os dados XML.</span><span class="sxs-lookup"><span data-stu-id="0a054-112">For the **XML data from variable** access mode, select the user-defined variable that contains the XML data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a054-113">As variáveis devem ser definidas no escopo da tarefa Fluxo de Dados que contém a origem XML ou no escopo do pacote, além disso, a variável deve ter um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0a054-113">The variables must be defined in the scope of the Data Flow task that contains the XML source, or in the scope of the package; additionally, the variable must have a string data type.</span></span>  
  
6.  <span data-ttu-id="0a054-114">Como opção, selecione **Usar esquema embutido** para indicar se o documento XML inclui informações de esquema.</span><span class="sxs-lookup"><span data-stu-id="0a054-114">Optionally, select **Use inline schema** to indicate that the XML document includes schema information.</span></span>  
  
7.  <span data-ttu-id="0a054-115">Para especificar um esquema XSD (linguagem de definição de esquema XML) externo para o arquivo XML, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="0a054-115">To specify an external XML Schema definition language (XSD) schema for the XML file, do one of the following:</span></span>  
  
    -   <span data-ttu-id="0a054-116">Clique em **Procurar** para localizar um arquivo XSD existente.</span><span class="sxs-lookup"><span data-stu-id="0a054-116">Click **Browse** to locate an existing XSD file.</span></span>  
  
    -   <span data-ttu-id="0a054-117">Clique em **Gerar XSD** para criar um XSD por meio do arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="0a054-117">Click **Generate XSD** to create an XSD from the XML file.</span></span>  
  
8.  <span data-ttu-id="0a054-118">Para atualizar os nomes das colunas de saída, clique em **Colunas** e edite os valores na lista **Coluna de Saída** .</span><span class="sxs-lookup"><span data-stu-id="0a054-118">To update the names of output columns, click **Columns** and edit the values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="0a054-119">Para configurar a saída de erro, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="0a054-119">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="0a054-120">Para obter mais informações, consulte [Configurar uma saída de erro em um componente de fluxo de dados](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0a054-120">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="0a054-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a054-121">Click **OK**.</span></span>  
  
11. <span data-ttu-id="0a054-122">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="0a054-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a054-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a054-123">See Also</span></span>  
 <span data-ttu-id="0a054-124">[Origem XML](xml-source.md) </span><span class="sxs-lookup"><span data-stu-id="0a054-124">[XML Source](xml-source.md) </span></span>  
 <span data-ttu-id="0a054-125">[Transformações do Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="0a054-125">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="0a054-126">[Caminhos do Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="0a054-126">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="0a054-127">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="0a054-127">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
