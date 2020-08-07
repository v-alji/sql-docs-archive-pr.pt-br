---
title: Conectando-se com o Editor de Consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 48725f54-a7b6-4b79-948e-965c1fe4eef1
author: stevestein
ms.author: sstein
ms.openlocfilehash: b50783450dfb9516c78a465806ee322d7a575377
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575511"
---
# <a name="connecting-with-query-editor"></a><span data-ttu-id="ed569-102">Conectando com o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="ed569-102">Connecting with Query Editor</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="ed569-103">permite que você escreva ou edite código enquanto estiver desconectado do servidor.</span><span class="sxs-lookup"><span data-stu-id="ed569-103">permits you to write or edit code while disconnected from the server.</span></span> <span data-ttu-id="ed569-104">Isso pode ser útil quando o servidor não estiver disponível ou quando você quiser conservar recursos escassos de rede ou servidor.</span><span class="sxs-lookup"><span data-stu-id="ed569-104">This can be useful when the server is not available or when you want to conserve scarce server or network resources.</span></span> <span data-ttu-id="ed569-105">Você também pode alterar a conexão do Editor de Consultas com uma instância nova do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sem abrir uma nova janela do editor ou redigitar o código.</span><span class="sxs-lookup"><span data-stu-id="ed569-105">You can also change the connection of Query Editor to a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without opening a new Query Editor window or retyping your code.</span></span>  
  
## <a name="coding-offline"></a><span data-ttu-id="ed569-106">Codificando offline</span><span class="sxs-lookup"><span data-stu-id="ed569-106">Coding Offline</span></span>  
  
#### <a name="to-write-code-offline-and-then-connect-to-different-servers"></a><span data-ttu-id="ed569-107">Para escrever código offline e depois se conectar a servidores diferentes</span><span class="sxs-lookup"><span data-stu-id="ed569-107">To write code offline and then connect to different servers</span></span>  
  
1.  <span data-ttu-id="ed569-108">Na barra de ferramentas do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , clique em **Consulta do Mecanismo de Banco de Dados** para abrir o Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="ed569-108">On the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] toolbar, click **Database Engine Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="ed569-109">Na caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** , clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="ed569-109">In the **Connect to Database Engine** dialog box, click **Cancel**.</span></span> <span data-ttu-id="ed569-110">O Editor de Consultas é aberto e a barra de título do editor indica que você não está conectado a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed569-110">The Query Editor opens, and the title bar for the Query Editor indicates that you are not connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="ed569-111">No painel de código, digite as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir:</span><span class="sxs-lookup"><span data-stu-id="ed569-111">In the code pane, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    SELECT * FROM Production.Product;  
    GO  
    ```  
  
     <span data-ttu-id="ed569-112">Neste ponto, você pode se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clicando em **Conectar**, **Executar**, **Analisar**ou **Exibir Plano de Execução Estimado**, disponíveis no menu **Consultar** , na barra de ferramentas do Editor de Consultas, ou no menu de atalho quando você clica com o botão direito do mouse na janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="ed569-112">At this point you can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by clicking **Connect**, **Execute**, **Parse**, or **Display Estimated Execution Plan**, all of which are available from either the **Query** menu, the Query Editor toolbar, or from the shortcut menu when you right-click in the Query Editor window.</span></span> <span data-ttu-id="ed569-113">Para esta prática, nós usaremos a barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="ed569-113">For this practice, we'll use the toolbar.</span></span>  
  
4.  <span data-ttu-id="ed569-114">Na barra de ferramentas, clique no botão **Executar** para abrir a caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ed569-114">On the toolbar, click the **Execute** button to open the **Connect to Database Engine** dialog box.</span></span>  
  
5.  <span data-ttu-id="ed569-115">Na caixa de texto **Nome do servidor** , digite o nome do servidor e clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="ed569-115">In the **Server name** text box, type your server name, and then click **Options**.</span></span>  
  
6.  <span data-ttu-id="ed569-116">Na guia **Propriedades da Conexão** , na lista **Conectar ao banco de dados** , procure o servidor para selecionar [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ed569-116">On the **Connection Properties** tab, in the **Connect to database** list, browse the server to select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="ed569-117">Para abrir outra janela do Editor de Consultas com a mesma conexão, na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ed569-117">To open another Query Editor window with the same connection, on the toolbar click **New Query**.</span></span>  
  
8.  <span data-ttu-id="ed569-118">Para alterar as conexões, clique com o botão direito do mouse na janela do Editor de Consultas, aponte para **Conexão**e clique em **Alterar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="ed569-118">To change connections, right-click in the Query Editor window, point to **Connection**, and then click **Change Connection**.</span></span>  
  
9. <span data-ttu-id="ed569-119">Na caixa de diálogo **Conectar ao SQL Server** , selecione outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se disponível, e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ed569-119">In the **Connect to SQL Server** dialog box, select another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if available, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="ed569-120">Esse recurso novo do Editor de Consultas permite a execução do mesmo código facilmente em vários servidores.</span><span class="sxs-lookup"><span data-stu-id="ed569-120">This new feature of Query Editor enables you to easily run the same code on several servers.</span></span> <span data-ttu-id="ed569-121">Isso pode ser útil para ações de manutenção que envolvem servidores semelhantes.</span><span class="sxs-lookup"><span data-stu-id="ed569-121">This may be useful for maintenance actions involving similar servers.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ed569-122">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="ed569-122">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ed569-123">Adicionando recuo</span><span class="sxs-lookup"><span data-stu-id="ed569-123">Adding Indentation</span></span>](lesson-2-2-adding-indentation.md)  
  
  
