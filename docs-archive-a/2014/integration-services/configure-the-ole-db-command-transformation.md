---
title: Configurar a transformação do comando OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [Integration Services]
- OLE DB Command transformation
ms.assetid: c800f167-3d2e-4c10-8ba3-a02f1872ccea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1714a6b798c6d8256052fd3c16bd86182480bcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684298"
---
# <a name="configure-the-ole-db-command-transformation"></a><span data-ttu-id="60ed4-102">Configurar a transformação Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="60ed4-102">Configure the OLE DB Command Transformation</span></span>
  <span data-ttu-id="60ed4-103">Para adicionar e configurar uma transformação Comando OLE DB, o pacote já deve incluir pelo menos uma tarefa Fluxo de Dados e uma origem, como, por exemplo, uma origem de arquivo simples ou uma origem de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="60ed4-103">To add and configure an OLE DB Command transformation, the package must already include at least one Data Flow task and a source such as a Flat File source or an OLE DB source.</span></span> <span data-ttu-id="60ed4-104">Essa transformação é normalmente usada para executar consultas parametrizadas.</span><span class="sxs-lookup"><span data-stu-id="60ed4-104">This transformation is typically used for running parameterized queries.</span></span>  
  
### <a name="to-configure-the-ole-db-command-transformation"></a><span data-ttu-id="60ed4-105">Para configurar a transformação Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="60ed4-105">To configure the OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="60ed4-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="60ed4-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="60ed4-107">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="60ed4-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="60ed4-108">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a transformação Comando OLE DB para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="60ed4-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB Command transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="60ed4-109">Conecte a transformação Comando OLE DB ao fluxo de dados arrastando um conector (a seta verde ou vermelha) de uma fonte de dados ou de uma transformação anterior para a transformação Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="60ed4-109">Connect the OLE DB Command transformation to the data flow by dragging a connector-the green or red arrow-from a data source or a previous transformation to the OLE DB Command transformation.</span></span>  
  
5.  <span data-ttu-id="60ed4-110">Com o botão direito do mouse, clique no componente e selecione Editar ou Mostrar **Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="60ed4-110">Right-click the component and select Edit or Show **Advanced Editor**.</span></span>  
  
6.  <span data-ttu-id="60ed4-111">Na guia **Gerenciadores de Conexões** , selecione um gerenciador de conexões OLE DB na lista **Gerenciador de Conexões** .</span><span class="sxs-lookup"><span data-stu-id="60ed4-111">On the **Connection Managers** tab, select an OLE DB connection manager in the **Connection Manager** list.</span></span> <span data-ttu-id="60ed4-112">Para obter mais informações, consulte [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="60ed4-112">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="60ed4-113">Clique na guia **Propriedades do Componente** e clique no botão de reticências **(...)** na caixa **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="60ed4-113">Click the **Component Properties** tab and click the ellipsis button **(...)** in the **SqlCommand** box.</span></span>  
  
8.  <span data-ttu-id="60ed4-114">No **Editor de Valores de Cadeias de Caracteres**, digite a instrução SQL parametrizada, com o uso de um ponto de interrogação (?) como o marcador para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="60ed4-114">In the **String Value Editor**, type the parameterized SQL statement using a question mark (?) as the parameter marker for each parameter.</span></span>  
  
9. <span data-ttu-id="60ed4-115">Clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="60ed4-115">Click **Refresh**.</span></span> <span data-ttu-id="60ed4-116">Quando você clica em **Atualizar**, a transformação cria uma coluna para cada parâmetro na coleção Colunas Externas e define a propriedade DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="60ed4-116">When you click **Refresh**, the transformation creates a column for each parameter in the External Columns collection and sets the DBParamInfoFlags property.</span></span>  
  
10. <span data-ttu-id="60ed4-117">Clique na guia **Propriedades de Entrada e Saída** .</span><span class="sxs-lookup"><span data-stu-id="60ed4-117">Click the **Input and Output Properties** tab.</span></span>  
  
11. <span data-ttu-id="60ed4-118">Expanda **Entrada de Comando OLE DB**e **Colunas Externas**.</span><span class="sxs-lookup"><span data-stu-id="60ed4-118">Expand **OLE DB Command Input**, and then expand **External Columns**.</span></span>  
  
12. <span data-ttu-id="60ed4-119">Verifique se **Colunas Externas** lista uma coluna para cada parâmetro na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="60ed4-119">Verify that **External Columns** lists a column for each parameter in the SQL statement.</span></span> <span data-ttu-id="60ed4-120">Os nomes das colunas são **Param_0**, **Param_1**e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="60ed4-120">The column names are **Param_0**, **Param_1**, and so on.</span></span>  
  
     <span data-ttu-id="60ed4-121">Você não deve alterar os nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="60ed4-121">You should not change the column names.</span></span> <span data-ttu-id="60ed4-122">Se você alterar os nomes de coluna, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gerará um erro de validação para a transformação Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="60ed4-122">If you change the column names, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a validation error for the OLE DB Command transformation.</span></span>  
  
     <span data-ttu-id="60ed4-123">Além disso, você não dever alterar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="60ed4-123">Also, you should not change the data type.</span></span> <span data-ttu-id="60ed4-124">A propriedade DataType de cada coluna é definida como o tipo de dados correto.</span><span class="sxs-lookup"><span data-stu-id="60ed4-124">The DataType property of each column is set to the correct data type.</span></span>  
  
13. <span data-ttu-id="60ed4-125">Se **Colunas Externas** não listar nenhuma coluna, você terá que adicioná-las manualmente.</span><span class="sxs-lookup"><span data-stu-id="60ed4-125">If **External Columns** lists no columns you must add them manually.</span></span>  
  
    -   <span data-ttu-id="60ed4-126">Clique em **Adicionar Coluna** uma vez para cada parâmetro na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="60ed4-126">Click **Add Column** one time for each parameter in the SQL statement.</span></span>  
  
    -   <span data-ttu-id="60ed4-127">Atualize os nomes das colunas para **Param_0**, **Param_1**, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="60ed4-127">Update the column names to **Param_0**, **Param_1**, and so on.</span></span>  
  
    -   <span data-ttu-id="60ed4-128">Especifique um valor na propriedade DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="60ed4-128">Specify a value in the DBParamInfoFlags property.</span></span> <span data-ttu-id="60ed4-129">O valor deve corresponder a um valor da enumeração OLE DB DBPARAMFLAGSENUM.</span><span class="sxs-lookup"><span data-stu-id="60ed4-129">The value must match a value in the OLE DB DBPARAMFLAGSENUM enumeration.</span></span> <span data-ttu-id="60ed4-130">Para obter mais informações, consulte a documentação de referência do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="60ed4-130">For more information, see the OLE DB reference documentation.</span></span>  
  
    -   <span data-ttu-id="60ed4-131">Especifique o tipo de dados da coluna e, dependendo do tipo de dados, especifique a página de código, o comprimento, a precisão e a escala da coluna.</span><span class="sxs-lookup"><span data-stu-id="60ed4-131">Specify the data type of the column and, depending on the data type, specify the code page, length, precision, and scale of the column.</span></span>  
  
    -   <span data-ttu-id="60ed4-132">Para excluir um parâmetro não utilizado, selecione o parâmetro em **Colunas Externas**e clique em **Remover Coluna**.</span><span class="sxs-lookup"><span data-stu-id="60ed4-132">To delete an unused parameter, select the parameter in **External Columns**, and then click **Remove Column**.</span></span>  
  
    -   <span data-ttu-id="60ed4-133">Clique em **Mapeamentos de Colunas** e mapeie colunas da lista **Colunas de Entrada Disponíveis** para parâmetros na lista **Colunas de Destino Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="60ed4-133">Click **Column Mappings** and map columns in the **Available Input Columns** list to parameters in the **Available Destination Columns** list.</span></span>  
  
14. <span data-ttu-id="60ed4-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60ed4-134">Click **OK**.</span></span>  
  
15. <span data-ttu-id="60ed4-135">Para salvar o pacote atualizado, clique em **Salvar** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="60ed4-135">To save the updated package, click **Save** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ed4-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60ed4-136">See Also</span></span>  
 <span data-ttu-id="60ed4-137">[Transformação de comando OLE DB](data-flow/transformations/ole-db-command-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="60ed4-137">[OLE DB Command Transformation](data-flow/transformations/ole-db-command-transformation.md) </span></span>  
 <span data-ttu-id="60ed4-138">[Transformações do Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="60ed4-138">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="60ed4-139">[Caminhos do Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="60ed4-139">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="60ed4-140">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="60ed4-140">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
