---
title: Criar uma conexão de modelo semântico de BI para uma pasta de trabalho PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b2e3f97f-18a8-42b6-9030-b4f818afc3b9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ea4ddcc38328acc6ff8cfb5387b13056b689a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581525"
---
# <a name="create-a-bi-semantic-model-connection-to-a-powerpivot-workbook"></a><span data-ttu-id="9c4fd-102">Criar uma conexão de modelo semântico de BI para uma pastas de trabalho PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9c4fd-102">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>
  <span data-ttu-id="9c4fd-103">Use as informações neste tópico para configurar uma conexão de modelo semântico do BI que redireciona para uma pastas de trabalho PowerPivot no mesmo farm.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-103">Use the information in this topic to set up a BI semantic model connection that redirects to a PowerPivot workbook in the same farm.</span></span>  
  
 <span data-ttu-id="9c4fd-104">Depois de criar uma conexão de modelo semântico de BI e configurar as permissões do SharePoint, você pode usá-lo como uma fonte de dados para Excel ou relatórios do [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c4fd-104">After you create a BI semantic model connection and configure SharePoint permissions, you can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="9c4fd-105">Este tópico inclui as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-105">This topic includes the following sections.</span></span> <span data-ttu-id="9c4fd-106">Execute cada tarefa na ordem fornecida.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="9c4fd-107">Examinar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9c4fd-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="9c4fd-108">Criar uma conexão</span><span class="sxs-lookup"><span data-stu-id="9c4fd-108">Create a Connection</span></span>](#bkmk_create)  
  
 [<span data-ttu-id="9c4fd-109">Configurar permissões do SharePoint na conexão de modelo semântico de BI</span><span class="sxs-lookup"><span data-stu-id="9c4fd-109">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="9c4fd-110">Configurar permissões do SharePoint na pasta de trabalho</span><span class="sxs-lookup"><span data-stu-id="9c4fd-110">Configure SharePoint Permissions on the Workbook</span></span>](#bkmk_userdb)  
  
 [<span data-ttu-id="9c4fd-111">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="9c4fd-111">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="9c4fd-112">Examinar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9c4fd-112">Review Prerequisites</span></span>  
 <span data-ttu-id="9c4fd-113">É necessário ter permissões Colaborar ou superior para criar um arquivo de conexão de modelo semântico de BI.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-113">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="9c4fd-114">Você deve ter uma biblioteca que dá suporte ao tipo de conteúdo da conexão de modelo semântico de BI.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-114">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="9c4fd-115">Para obter mais informações, consulte [Adicionar um tipo de conteúdo de conexão de modelo semântico de bi a uma biblioteca &#40;PowerPivot para SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="9c4fd-115">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="9c4fd-116">Você deve saber a URL da pasta de trabalho PowerPivot para a qual está configurando uma conexão de modelo semântico de BI (por exemplo, http://adventure-works/shared documentos/myworkbook.xlsx).</span><span class="sxs-lookup"><span data-stu-id="9c4fd-116">You must know the URL of the PowerPivot workbook for which you are setting up a BI semantic model connection (for example, http://adventure-works/shared documents/myworkbook.xlsx).</span></span> <span data-ttu-id="9c4fd-117">A pasta de trabalho deve estar no mesmo farm.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-117">The workbook must be in the same farm.</span></span>  
  
 <span data-ttu-id="9c4fd-118">Todos os computadores e usuários que participam da sequência de conexão devem estar no mesmo domínio ou domínio confiável (confiança bidirecional).</span><span class="sxs-lookup"><span data-stu-id="9c4fd-118">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="create-a-connection"></a><a name="bkmk_create"></a><span data-ttu-id="9c4fd-119">Criar uma conexão</span><span class="sxs-lookup"><span data-stu-id="9c4fd-119">Create a Connection</span></span>  
  
1.  <span data-ttu-id="9c4fd-120">Na biblioteca que conterá a conexão de modelo semântico de BI, clique em **Documentos** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-120">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span> <span data-ttu-id="9c4fd-121">Clique na seta para baixo em Novo Documento e selecione **Arquivo de Conexão de BISM** para abrir uma nova página de Conexão de Modelo Semântico de BI.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-121">Click the down arrow on New Document, and select **BISM Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
     <span data-ttu-id="9c4fd-122">![Submenu Novo Documento em uma biblioteca do SharePoint](../media/ssas-bismconnection-new.gif "Submenu Novo Documento em uma biblioteca do SharePoint")</span><span class="sxs-lookup"><span data-stu-id="9c4fd-122">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
2.  <span data-ttu-id="9c4fd-123">Defina a propriedade **Server** como a URL do SharePoint da pasta de trabalho PowerPivot (por exemplo, \*\* http://mysharepoint/shared Documents/myWorkbook.xlsx\*\*.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-123">Set the **Server** property to the SharePoint URL of the PowerPivot workbook (for example, **http://mysharepoint/shared documents/myWorkbook.xlsx**.</span></span> <span data-ttu-id="9c4fd-124">Em uma implantação do PowerPivot para SharePoint, dados podem ser carregados em qualquer servidor no farm.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-124">In a PowerPivot for SharePoint deployment, data can be loaded on any server in the farm.</span></span> <span data-ttu-id="9c4fd-125">Por isso, as conexões da fonte de dados para dados PowerPivot especificam apenas o caminho para a pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-125">For this reason, data source connections to PowerPivot data specify just the path to the workbook.</span></span> <span data-ttu-id="9c4fd-126">O Serviço de Sistema do PowerPivot determina qual servidor carrega os dados.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-126">The PowerPivot System Service determines which server loads the data.</span></span>  
  
     <span data-ttu-id="9c4fd-127">Não usar a propriedade de **banco de dados** ; Ele não é usado ao especificar o local de uma pasta de trabalho PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-127">Do not use the **Database** property; it is not used when specifying the location of a PowerPivot workbook.</span></span>  
  
     <span data-ttu-id="9c4fd-128">Sua página deve ser similar à ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-128">Your page should look similar to the following illustration.</span></span>  
  
     <span data-ttu-id="9c4fd-129">![Página de conexão BISM mostrando URL para pasta de trabalho](../media/ssas-bismconnection-ppvtds.gif "Página de conexão BISM mostrando URL para pasta de trabalho")</span><span class="sxs-lookup"><span data-stu-id="9c4fd-129">![BISM connection page showing URL to workbook](../media/ssas-bismconnection-ppvtds.gif "BISM connection page showing URL to workbook")</span></span>  
  
     <span data-ttu-id="9c4fd-130">Opcionalmente, se você tiver permissões do SharePoint para a pasta de trabalho, uma etapa de validação adicional será executada, garantindo que o local seja válido.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-130">Optionally, if you have SharePoint permissions to the workbook, an extra validation step is performed, ensuring that the location is valid.</span></span> <span data-ttu-id="9c4fd-131">Se você não tiver permissão para acessar os dados, terá a opção de salvar a conexão de modelo semântico de BI sem a resposta de validação.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-131">If you do not have permission to access the data, you are given the option of saving the BI semantic model connection without the validation response.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a><span data-ttu-id="9c4fd-132">Configurar permissões do SharePoint na conexão de modelo semântico de BI</span><span class="sxs-lookup"><span data-stu-id="9c4fd-132">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="9c4fd-133">A capacidade para usar uma conexão de modelo semântico de BI como uma fonte de dados para uma pasta de trabalho do Excel ou relatório do Reporting Services exige permissões de **Leitura** no item de conexão do modelo semântico de BI em uma biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-133">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="9c4fd-134">O nível de permissão de leitura inclui a permissão **Abrir Itens** que habilita o carregamento de informações da conexão de modelo semântico de BI em um aplicativo de área de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-134">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="9c4fd-135">Há várias maneiras de conceder permissões no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-135">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="9c4fd-136">As instruções a seguir explicam como criar um novo grupo chamado **Usuários do BISM** que tem o nível de permissão de **Leitura** .</span><span class="sxs-lookup"><span data-stu-id="9c4fd-136">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="9c4fd-137">Você deve ser proprietário do site para alterar permissões.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-137">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="9c4fd-138">Em Ações do Site, clique em **Permissões do Site**.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-138">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="9c4fd-139">Clique em **Criar Grupo** e dê o nome de **Usuários do BISM**ao novo grupo.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-139">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="9c4fd-140">Escolha o nível de permissão de **Leitura** e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-140">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="9c4fd-141">Selecione **Usuários do BISM** em Pessoas e Grupos.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-141">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="9c4fd-142">Aponte para Novo, clique em **Adicionar Usuários**e adicione contas de usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-142">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="9c4fd-143">Estes usuários e grupos agora terão permissões de Leitura em todo o site, incluindo todas as bibliotecas e listas que herdam permissões do nível do site.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-143">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="9c4fd-144">Se estas permissões forem muito altas, você poderá remover este grupo seletivamente de bibliotecas específicas, listas ou itens.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-144">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="9c4fd-145">Para remover permissões seletivamente no nível do item, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c4fd-145">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="9c4fd-146">Em uma biblioteca, selecione um documento.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-146">In a library, select a document.</span></span> <span data-ttu-id="9c4fd-147">Clique na seta para baixo à direita e clique em **Gerenciar Permissões**.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-147">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="9c4fd-148">Por padrão, um item herda permissões.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-148">By default, an item inherits permissions.</span></span> <span data-ttu-id="9c4fd-149">Para alterar as permissões de documentos individuais nessa biblioteca, clique em **Parar de Herdar Permissões**.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-149">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="9c4fd-150">Marque a caixa de seleção junto a **Usuários do BISM**.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-150">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="9c4fd-151">Clique em **Remover Permissões do Usuário**.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-151">Click **Remove User Permissions**.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-workbook"></a><a name="bkmk_userdb"></a><span data-ttu-id="9c4fd-152">Configurar permissões do SharePoint na pasta de trabalho</span><span class="sxs-lookup"><span data-stu-id="9c4fd-152">Configure SharePoint Permissions on the Workbook</span></span>  
 <span data-ttu-id="9c4fd-153">Se você estiver usando um banco de dados PowerPivot dentro de uma pasta de trabalho do Excel, as permissões do SharePoint na pasta de trabalho do Excel determinarão o acesso a dados pela conexão de modelo semântico de BI.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-153">If you are using a PowerPivot database inside an Excel workbook, the SharePoint permissions on the Excel workbook determine data access via the BI semantic model connection.</span></span> <span data-ttu-id="9c4fd-154">Todos os usuários que acessam a pasta de trabalho devem ter permissões de Leitura na pasta de trabalho para usá-la como uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-154">All users who access the workbook must have Read permissions on the workbook in order to use it as an external data source.</span></span>  
  
 <span data-ttu-id="9c4fd-155">Se você tiver criado um grupo de **Usuários de BISM** usando as instruções na seção anterior, as contas de usuário e grupo que são membros de **Usuários de BISM** terão permissões suficientes na pasta de trabalho, assim como o arquivo de conexão do modelo semântico de BI, contanto que a pasta de trabalho use permissões herdadas.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-155">If you created a **BISM Users** group using the instructions in the previous section, user and group accounts that are members of **BISM Users** will have sufficient permission on the workbook as well as the BI semantic model connection file, assuming the workbook uses inherited permissions.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="9c4fd-156">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="9c4fd-156">Next Steps</span></span>  
 <span data-ttu-id="9c4fd-157">Depois de criar e proteger uma conexão de modelo semântico de BI, você poderá especificá-la como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9c4fd-157">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="9c4fd-158">Para obter mais informações, consulte [Usar uma conexão de modelo semântico de BI no Excel ou Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c4fd-158">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4fd-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c4fd-159">See Also</span></span>  
 <span data-ttu-id="9c4fd-160">[Conexão de modelo semântico de BI do PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="9c4fd-160">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 <span data-ttu-id="9c4fd-161">[Usar uma conexão de modelo semântico de BI no Excel ou Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="9c4fd-161">[Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span></span>  
 [<span data-ttu-id="9c4fd-162">Create a BI Semantic Model Connection to a Tabular Model Database</span><span class="sxs-lookup"><span data-stu-id="9c4fd-162">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
  
