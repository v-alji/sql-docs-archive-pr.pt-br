---
title: Mapear parâmetros de consulta para variáveis em um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 5e26977c-758c-46d6-acf1-4fd9238f0950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b38940313397c7be7a8bcdbd2bf7f5233583096e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685220"
---
# <a name="map-query-parameters-to-variables-in-a-data-flow-component"></a><span data-ttu-id="c20cb-102">Mapear parâmetros de consulta para variáveis em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="c20cb-102">Map Query Parameters to Variables in a Data Flow Component</span></span>
  <span data-ttu-id="c20cb-103">Quando você configura a fonte OLE DB para usar consultas parametrizadas, pode mapear os parâmetros para variáveis.</span><span class="sxs-lookup"><span data-stu-id="c20cb-103">When you configure the OLE DB source to use parameterized queries, you can map the parameters to variables.</span></span>  
  
 <span data-ttu-id="c20cb-104">As fontes OLE DB usam consultas parametrizadas para filtrar dados quando a fonte conecta-se a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c20cb-104">The OLE DB source uses parameterized queries to filter data when the source connects to a data source.</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="c20cb-105">Para mapear um parâmetro de consulta para uma variável</span><span class="sxs-lookup"><span data-stu-id="c20cb-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="c20cb-106">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="c20cb-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c20cb-107">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="c20cb-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="c20cb-108">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a fonte OLE DB para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c20cb-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="c20cb-109">Clique com o botão direito do mouse na fonte OLE DB e, depois, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c20cb-109">Right-click the OLE DB source, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="c20cb-110">Em **Editor de Origem OLE DB**, selecione um gerenciador de conexões para usar para conectar-se à fonte de dados ou clique em **Novo** para criar um novo gerenciador de conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c20cb-110">In the **OLE DB Source Editor**, select an OLE DB connection manager to use to connect to the data source, or click **New** to create a new OLE DB connection manager.</span></span>  
  
6.  <span data-ttu-id="c20cb-111">Selecione a opção de **Comando SQL** para o modo de acesso a dados e, então, digite uma consulta parametrizada no painel **Texto de comando SQL** .</span><span class="sxs-lookup"><span data-stu-id="c20cb-111">Select the **SQL command** option for data access mode, and then type a parameterized query in the **SQL command text** pane.</span></span>  
  
7.  <span data-ttu-id="c20cb-112">Clique em **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="c20cb-112">Click **Parameters**.</span></span>  
  
8.  <span data-ttu-id="c20cb-113">Na caixa de diálogo **Definir Parâmetros de Consulta**, mapeie cada parâmetro na lista **Parâmetros** para uma variável na lista **Variáveis** ou crie uma variável clicando em **\<New variable>** .</span><span class="sxs-lookup"><span data-stu-id="c20cb-113">In the **Set Query Parameters** dialog box, map each parameter in the **Parameters** list to a variable in the **Variables** list, or create a new variable by clicking **\<New variable>**.</span></span> <span data-ttu-id="c20cb-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c20cb-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c20cb-115">Apenas as variáveis do sistema e as variáveis definidas pelo usuário que estão no escopo do pacote, um contêiner pai como Loop Foreach ou a tarefa de Fluxo de Dados que contém o componente de fluxo de dados, estão disponíveis para mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c20cb-115">Only system variables and user-defined variables that are in the scope of the package, a parent container such as a Foreach Loop, or the Data Flow task that contains the data flow component are available for mapping.</span></span> <span data-ttu-id="c20cb-116">A variável deve ter um tipo de dados que seja compatível com a coluna na cláusula WHERE, para a qual o parâmetro é designado.</span><span class="sxs-lookup"><span data-stu-id="c20cb-116">The variable must have a data type that is compatible with the column in the WHERE clause to which the parameter is assigned.</span></span>  
  
9. <span data-ttu-id="c20cb-117">Você pode clicar em **Visualizar** para exibir até 200 linhas dos dados que a consulta retorna.</span><span class="sxs-lookup"><span data-stu-id="c20cb-117">You can click **Preview** to view up to 200 rows of the data that the query returns.</span></span>  
  
10. <span data-ttu-id="c20cb-118">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="c20cb-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c20cb-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c20cb-119">See Also</span></span>  
 <span data-ttu-id="c20cb-120">[Origem de OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="c20cb-120">[OLE DB Source](ole-db-source.md) </span></span>  
 [<span data-ttu-id="c20cb-121">Transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="c20cb-121">Lookup Transformation</span></span>](transformations/lookup-transformation.md)  
  
  
