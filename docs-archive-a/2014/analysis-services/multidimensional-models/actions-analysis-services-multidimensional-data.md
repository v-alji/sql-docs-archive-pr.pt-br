---
title: Ações (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services]
- actions [Analysis Services], about actions
- MDX [Analysis Services], actions
- cubes [Analysis Services], actions
- OLAP objects [Analysis Services], actions
ms.assetid: 07229bb2-805c-427e-8455-69c9ca5d01e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: d19c14c68a81b38ee052dba270f3f734860f8045
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572762"
---
# <a name="actions-analysis-services---multidimensional-data"></a><span data-ttu-id="6325d-102">Ações (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="6325d-102">Actions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6325d-103">As ações podem ser de tipos diferentes e devem ser criadas adequadamente.</span><span class="sxs-lookup"><span data-stu-id="6325d-103">Actions can be of different types and they have to be created accordingly.</span></span> <span data-ttu-id="6325d-104">As ações podem ser:</span><span class="sxs-lookup"><span data-stu-id="6325d-104">Actions can be:</span></span>  
  
-   <span data-ttu-id="6325d-105">Ações de detalhamento, que retornam o conjunto de linhas que representa os dados subjacentes das células selecionadas do cubo onde a ação ocorre.</span><span class="sxs-lookup"><span data-stu-id="6325d-105">Drillthrough actions, which return the set of rows that represents the underlying data of the selected cells of the cube where the action occurs.</span></span>  
  
-   <span data-ttu-id="6325d-106">Ações de relatório, que retornam um relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] associado a uma seção selecionada do cubo onde a ação ocorre.</span><span class="sxs-lookup"><span data-stu-id="6325d-106">Reporting actions, which return a report from [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is associated with the selected section of the cube where the action occurs.</span></span>  
  
-   <span data-ttu-id="6325d-107">Ações padrão, que retornam o elemento de ação (URL, HTML, DataSet, RowSet e outros elementos) associado a uma seção selecionada do cubo onde a ação ocorre.</span><span class="sxs-lookup"><span data-stu-id="6325d-107">Standard actions, which return the action element (URL, HTML, DataSet, RowSet, and other elements) that is associated with the selected section of the cube where the action occurs.</span></span>  
  
 <span data-ttu-id="6325d-108">Uma interface de consulta, como ADOMD.NET, é usada pelo aplicativo cliente para recuperar e expor as ações ao usuário final.</span><span class="sxs-lookup"><span data-stu-id="6325d-108">A query interface, such as ADOMD.NET, is used by the client application to retrieve and expose the actions to the end user.</span></span> <span data-ttu-id="6325d-109">Para obter mais informações, consulte [Desenvolvendo com ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net).</span><span class="sxs-lookup"><span data-stu-id="6325d-109">For more information see [Developing with ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net).</span></span>  
  
 <span data-ttu-id="6325d-110">Um objeto simples <xref:Microsoft.AnalysisServices.Action> é composto de: informações básicas, o destino no qual a ação deve ocorrer, uma condição para limitar o escopo da ação e o tipo.</span><span class="sxs-lookup"><span data-stu-id="6325d-110">A simple <xref:Microsoft.AnalysisServices.Action> object is composed of: basic information, the target where the action is to occur, a condition to limit the action scope, and the type.</span></span> <span data-ttu-id="6325d-111">As informações básicas incluem o nome da ação, sua descrição, a legenda sugerida e outros.</span><span class="sxs-lookup"><span data-stu-id="6325d-111">Basic information includes the name of the action, the description of the action, the caption suggested for the action, and others.</span></span>  
  
 <span data-ttu-id="6325d-112">O destino é o local real no cubo onde a ação deve acontecer.</span><span class="sxs-lookup"><span data-stu-id="6325d-112">The target is the actual location in the cube where the action is to occur.</span></span> <span data-ttu-id="6325d-113">O destino é composto de um tipo de destino e um objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="6325d-113">The target is composed of a target type and a target object.</span></span> <span data-ttu-id="6325d-114">O tipo de destino representa o tipo de objeto, no cubo, onde a ação será habilitada.</span><span class="sxs-lookup"><span data-stu-id="6325d-114">Target type represents the kind of object, in the cube, where the action is to be enabled.</span></span> <span data-ttu-id="6325d-115">Tipo de destino pode ser membros de nível, células, hierarquia, membros de hierarquia ou outros.</span><span class="sxs-lookup"><span data-stu-id="6325d-115">Target type could be level members, cells, hierarchy, hierarchy members, or others.</span></span> <span data-ttu-id="6325d-116">O objeto de destino for um objeto específico do tipo de destino, se o tipo de destino for hierarquia, então o objeto de destino será qualquer uma das hierarquias definidas no cubo.</span><span class="sxs-lookup"><span data-stu-id="6325d-116">The target object is a specific object of the target type; if the target type is hierarchy, then the target object is any one of the defined hierarchies in the cube.</span></span>  
  
 <span data-ttu-id="6325d-117">A condição é uma expressão MDX `Boolean` avaliada no evento da ação.</span><span class="sxs-lookup"><span data-stu-id="6325d-117">The condition is a `Boolean` MDX expression that is evaluated at the action event.</span></span> <span data-ttu-id="6325d-118">Se a condição for avaliada como `true`, então, a ação será executada.</span><span class="sxs-lookup"><span data-stu-id="6325d-118">If the condition evaluates to `true`, then the action is executed.</span></span> <span data-ttu-id="6325d-119">Caso contrário, a ação não será executada.</span><span class="sxs-lookup"><span data-stu-id="6325d-119">Otherwise, the action is not executed.</span></span>  
  
 <span data-ttu-id="6325d-120">O tipo é a forma de ação a ser executada.</span><span class="sxs-lookup"><span data-stu-id="6325d-120">The type is the kind of action to be executed.</span></span> <span data-ttu-id="6325d-121"><xref:Microsoft.AnalysisServices.Action> é uma classe abstrata, portanto, a ser usada se precisar usar uma das classes derivadas.</span><span class="sxs-lookup"><span data-stu-id="6325d-121"><xref:Microsoft.AnalysisServices.Action> is an abstract class, therefore, to use it you have to use any one of the derived classes.</span></span> <span data-ttu-id="6325d-122">Dois tipos de ações são predefinidos: análise e relatório.</span><span class="sxs-lookup"><span data-stu-id="6325d-122">Two kinds of actions are predefined: drillthrough and reporting.</span></span> <span data-ttu-id="6325d-123">Elas têm classes derivadas correspondentes: <xref:Microsoft.AnalysisServices.DrillThroughAction> e <xref:Microsoft.AnalysisServices.ReportAction>.</span><span class="sxs-lookup"><span data-stu-id="6325d-123">These have corresponding derived classes: <xref:Microsoft.AnalysisServices.DrillThroughAction> and <xref:Microsoft.AnalysisServices.ReportAction>.</span></span> <span data-ttu-id="6325d-124">Outras ações são abrangidas na classe <xref:Microsoft.AnalysisServices.StandardAction> .</span><span class="sxs-lookup"><span data-stu-id="6325d-124">Other actions are covered in the <xref:Microsoft.AnalysisServices.StandardAction> class.</span></span>  
  
 <span data-ttu-id="6325d-125">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , uma ação é uma instrução MDX armazenada que pode ser apresentada e empregada por aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="6325d-125">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an action is a stored MDX statement that can be presented to and employed by client applications.</span></span> <span data-ttu-id="6325d-126">Em outras palavras, uma ação é um comando cliente definido e armazenado no servidor.</span><span class="sxs-lookup"><span data-stu-id="6325d-126">In other words, an action is a client command that is defined and stored on the server.</span></span> <span data-ttu-id="6325d-127">Uma ação também contém informações que especificam quando e como uma instrução MDX deve ser exibida e tratada pelo aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="6325d-127">An action also contains information that specifies when and how the MDX statement should be displayed and handled by the client application.</span></span> <span data-ttu-id="6325d-128">A operação especificada pela ação pode iniciar um aplicativo, usando as informações na ação como um parâmetro ou pode recuperar informações com base em critérios fornecidos pela ação.</span><span class="sxs-lookup"><span data-stu-id="6325d-128">The operation that is specified by the action can start an application, using the information in the action as a parameter, or can retrieve information based on criteria supplied by the action.</span></span>  
  
 <span data-ttu-id="6325d-129">As ações permitem que usuários empresariais ajam nos resultados de suas análises.</span><span class="sxs-lookup"><span data-stu-id="6325d-129">Actions enable business users to act upon the outcomes of their analyses.</span></span> <span data-ttu-id="6325d-130">Salvando e reusando ações, os usuários finais podem ir além da análise tradicional, que geralmente termina com a apresentação de dados e inicia soluções para problemas e deficiências descobertas, estendendo assim os aplicativos de business intelligence além do cubo.</span><span class="sxs-lookup"><span data-stu-id="6325d-130">By saving and reusing actions, end users can go beyond traditional analysis, which typically ends with presentation of data, and initiate solutions to discovered problems and deficiencies, thereby extending the business intelligence application beyond the cube.</span></span> <span data-ttu-id="6325d-131">As ações podem transformar o aplicativo cliente de uma ferramenta de renderização de dados sofisticada em parte integral do sistema operacional da empresa.</span><span class="sxs-lookup"><span data-stu-id="6325d-131">Actions can transform the client application from a sophisticated data rendering tool into an integral part of the enterprise's operational system.</span></span> <span data-ttu-id="6325d-132">Em vez de focalizar os dados de envio como entrada de aplicativos operacionais, os usuários finais "fecham o ciclo" do processo de tomada de decisões.</span><span class="sxs-lookup"><span data-stu-id="6325d-132">Instead of focusing on  sending data as input to operational applications, end users can "close the loop" on the decision-making process.</span></span> <span data-ttu-id="6325d-133">Essa capacidade de transformar dados analíticos em decisões é crucial para o sucesso do aplicativo Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="6325d-133">This ability to transform analytical data into decisions is crucial to the successful business intelligence application.</span></span>  
  
 <span data-ttu-id="6325d-134">Por exemplo, um usuário empresarial que navega em um cubo observa que o estoque atual de um determinado produto está baixo.</span><span class="sxs-lookup"><span data-stu-id="6325d-134">For example, a business user browsing a cube notices that the current stock of a certain product is low.</span></span> <span data-ttu-id="6325d-135">O aplicativo cliente fornece ao usuário empresarial uma lista de ações, todas relacionadas ao valor de baixo estoque do produto, recuperadas do banco de dados do Analysis Services; o usuário empresarial selecionar a ação Pedido para o membro do cubo que representa o produto.</span><span class="sxs-lookup"><span data-stu-id="6325d-135">The client application provides to the business user a list of actions, all related to low product stock value, that are retrieved from the Analysis Services database, The business user selects the Order action for the member of the cube that represents the product.</span></span> <span data-ttu-id="6325d-136">A ação Pedido inicia um novo pedido chamando o procedimento armazenado no banco de dados operacional.</span><span class="sxs-lookup"><span data-stu-id="6325d-136">The Order action initiates a new order by calling a stored procedure in the operational database.</span></span> <span data-ttu-id="6325d-137">Esse procedimento armazenado gera as informações apropriadas para enviar a serem enviadas ao sistema de entrada de pedidos.</span><span class="sxs-lookup"><span data-stu-id="6325d-137">This stored procedure generates the appropriate information to send to the order entry system.</span></span>  
  
 <span data-ttu-id="6325d-138">Há flexibilidade na criação de ações: por exemplo, uma ação pode iniciar um aplicativo ou recuperar informações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6325d-138">You can exercise flexibility when you create actions: for example, an action can launch an application, or retrieve information from a database.</span></span> <span data-ttu-id="6325d-139">Você pode configurar uma ação a ser disparada de praticamente qualquer parte de um cubo, incluindo dimensões, níveis, membros e células ou criar várias ações para a mesma parte de um cubo.</span><span class="sxs-lookup"><span data-stu-id="6325d-139">You can configure an action to be triggered from almost any part of a cube, including dimensions, levels, members, and cells, or create multiple actions for the same portion of a cube.</span></span> <span data-ttu-id="6325d-140">Você também pode passar parâmetros de cadeia de caracteres para os aplicativos iniciados e especificar as legendas exibidas aos usuários finais à medida que a ação é executada.</span><span class="sxs-lookup"><span data-stu-id="6325d-140">You can also pass string parameters to the launched applications and specify the captions displayed to end users as the action runs.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6325d-141">Para que um usuário empresarial use as ações, o aplicativo cliente empregado pelo usuário empresarial deve oferecer suporte a ações.</span><span class="sxs-lookup"><span data-stu-id="6325d-141">In order for a business user to use actions, the client application employed by the business user must support actions.</span></span>  
  
## <a name="types-of-actions"></a><span data-ttu-id="6325d-142">Tipos de ações</span><span class="sxs-lookup"><span data-stu-id="6325d-142">Types of Actions</span></span>  
 <span data-ttu-id="6325d-143">A tabela a seguir lista os tipos de ações incluídos em [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6325d-143">The following table lists the types of actions that are included in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]:</span></span>  
  
|<span data-ttu-id="6325d-144">Tipo de ação</span><span class="sxs-lookup"><span data-stu-id="6325d-144">Action Type</span></span>|<span data-ttu-id="6325d-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="6325d-145">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6325d-146">CommandLine</span><span class="sxs-lookup"><span data-stu-id="6325d-146">CommandLine</span></span>|<span data-ttu-id="6325d-147">Executa um comando no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="6325d-147">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="6325d-148">Conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="6325d-148">Dataset</span></span>|<span data-ttu-id="6325d-149">Retorna um conjunto de dados a um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="6325d-149">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="6325d-150">Detalhamento</span><span class="sxs-lookup"><span data-stu-id="6325d-150">Drillthrough</span></span>|<span data-ttu-id="6325d-151">Retorna uma instrução de detalhamento como uma expressão e que o cliente executa para retornar um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="6325d-151">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="6325d-152">Html</span><span class="sxs-lookup"><span data-stu-id="6325d-152">Html</span></span>|<span data-ttu-id="6325d-153">Executa um script HTML em um navegador de Internet.</span><span class="sxs-lookup"><span data-stu-id="6325d-153">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="6325d-154">Proprietário</span><span class="sxs-lookup"><span data-stu-id="6325d-154">Proprietary</span></span>|<span data-ttu-id="6325d-155">Executa uma operação usando uma interface diferente das listadas nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="6325d-155">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="6325d-156">Relatório</span><span class="sxs-lookup"><span data-stu-id="6325d-156">Report</span></span>|<span data-ttu-id="6325d-157">Envia uma solicitação com base em URL parametrizada para um servidor de relatórios e retorna um relatório a um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="6325d-157">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="6325d-158">Conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="6325d-158">Rowset</span></span>|<span data-ttu-id="6325d-159">Retorna um conjunto de linhas a um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="6325d-159">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="6325d-160">Instrução</span><span class="sxs-lookup"><span data-stu-id="6325d-160">Statement</span></span>|<span data-ttu-id="6325d-161">Executa um comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="6325d-161">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="6325d-162">URL</span><span class="sxs-lookup"><span data-stu-id="6325d-162">URL</span></span>|<span data-ttu-id="6325d-163">Exibe uma página da Web dinâmica em um navegador de Internet.</span><span class="sxs-lookup"><span data-stu-id="6325d-163">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
## <a name="resolving-and-executing-actions"></a><span data-ttu-id="6325d-164">Resolvendo e executando ações</span><span class="sxs-lookup"><span data-stu-id="6325d-164">Resolving and Executing Actions</span></span>  
 <span data-ttu-id="6325d-165">Quando um usuário empresarial acessa o objeto pra o qual o objeto de comando está definido, a instrução associada à ação é automaticamente resolvida, o que o torna disponível para o aplicativo cliente, mas a ação não é executada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6325d-165">When a business user accesses the object for which the command object is defined, the statement associated with the action is automatically resolved, which makes it available to the client application, but the action is not automatically executed.</span></span> <span data-ttu-id="6325d-166">A ação só é executada quando o usuário empresarial executar a operação específica ao cliente que inicia a ação.</span><span class="sxs-lookup"><span data-stu-id="6325d-166">The action is executed only when the business user performs the client-specific operation that initiates the action.</span></span> <span data-ttu-id="6325d-167">Por exemplo, um aplicativo cliente pode exibir uma lista de ações como menu pop-up, quando o usuário empresarial clica com o botão direito do mouse em um membro ou célula em particular.</span><span class="sxs-lookup"><span data-stu-id="6325d-167">For example, a client applications might display a list of actions as a pop-up menu when the business user right-clicks on a particular member or cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6325d-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6325d-168">See Also</span></span>  
 [<span data-ttu-id="6325d-169">Ações em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="6325d-169">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)  
  
  