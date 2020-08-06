---
title: Conceitos básicos do pacote SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c58ddc13b5c149b84fa550f312782b02786d062
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681774"
---
# <a name="ssis-package-essentials"></a><span data-ttu-id="42e84-102">Informações essenciais sobre pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="42e84-102">SSIS Package Essentials</span></span>
  <span data-ttu-id="42e84-103">Um pacote é o objeto que implementa a funcionalidade do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para extrair, transformar e carregar dados.</span><span class="sxs-lookup"><span data-stu-id="42e84-103">A package is the object that implements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] functionality to extract, transform, and load data.</span></span> <span data-ttu-id="42e84-104">Crie um pacote usando o Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42e84-104">You create a package by using the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="42e84-105">Você também pode criar um pacote executando o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou o Assistente para Conexões de Projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42e84-105">You can also create a package by running the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard or the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Connections Project Wizard.</span></span> <span data-ttu-id="42e84-106">Para obter mais informações, [crie pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) no designer do SSIS e no [Assistente de importação de projeto](../../2014/integration-services/import-project-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="42e84-106">For more information, [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS Designer and [Import Project Wizard](../../2014/integration-services/import-project-wizard.md).</span></span>  
  
 <span data-ttu-id="42e84-107">Um pacote básico inclui os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="42e84-107">A basic package includes the following elements:</span></span>  
  
 <span data-ttu-id="42e84-108">**Elementos de fluxo de controle**</span><span class="sxs-lookup"><span data-stu-id="42e84-108">**Control flow elements**</span></span>  
 <span data-ttu-id="42e84-109">Esses elementos obrigatórios executam várias funções, fornecem estrutura e controlam a ordem em que os elementos são executados.</span><span class="sxs-lookup"><span data-stu-id="42e84-109">These required elements perform various functions, provide structure, and control the order in which elements run.</span></span> <span data-ttu-id="42e84-110">Os elementos de fluxo de controle principais são as tarefas, os contêineres e as restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="42e84-110">The main control flow elements are tasks, containers, and precedence constraints.</span></span> <span data-ttu-id="42e84-111">Deve haver pelo menos um elemento de fluxo de controle em um pacote.</span><span class="sxs-lookup"><span data-stu-id="42e84-111">There must be at least one control flow element in a package.</span></span>  
  
 <span data-ttu-id="42e84-112">Para obter mais informações, consulte [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="42e84-112">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="42e84-113">**Elementos de fluxo de dados**</span><span class="sxs-lookup"><span data-stu-id="42e84-113">**Data flow elements**</span></span>  
 <span data-ttu-id="42e84-114">Esses elementos opcionais extraem, modificam e carregam dados em fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="42e84-114">These optional elements extract data, modify data, and load data into data sources.</span></span> <span data-ttu-id="42e84-115">Os elementos de fluxo de dados principais são fontes, transformações e destinos.</span><span class="sxs-lookup"><span data-stu-id="42e84-115">The main data flow elements are sources, transformations, and destinations.</span></span> <span data-ttu-id="42e84-116">Não é necessário haver elementos de fluxo de dados no pacote.</span><span class="sxs-lookup"><span data-stu-id="42e84-116">There does not have to be any data flow elements in package.</span></span>  
  
 <span data-ttu-id="42e84-117">Para obter mais informações, consulte [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="42e84-117">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="42e84-118">Para obter um exemplo de como criar um pacote básico, consulte [lição 1: criando o projeto e o pacote básico](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="42e84-118">For an example of how to create a basic package, see [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="42e84-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="42e84-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="42e84-120">Criar pacotes nas Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="42e84-120">Create Packages in SQL Server Data Tools</span></span>](create-packages-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="42e84-121">Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="42e84-121">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [<span data-ttu-id="42e84-122">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="42e84-122">Set the Properties of a Task or Container</span></span>](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [<span data-ttu-id="42e84-123">Adicionar ou excluir um componente em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="42e84-123">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a><span data-ttu-id="42e84-124">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="42e84-124">Related Content</span></span>  
  
1.  <span data-ttu-id="42e84-125">Vídeo, [Criando um pacote básico (vídeo do SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131023), no site MSDN.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="42e84-125">Video, [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023), on MSDN.Microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e84-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42e84-126">See Also</span></span>  
 <span data-ttu-id="42e84-127">[Integration Services &#40;os pacotes&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="42e84-127">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="42e84-128">Restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="42e84-128">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  
