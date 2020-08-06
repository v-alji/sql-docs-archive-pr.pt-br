---
title: Desconectar usuários e sessões no Analysis Services Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: bac20b663b0a65902c70e7a3c3bfe3f27b7bf061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680150"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a><span data-ttu-id="60131-102">Desconectar usuários e sessões no Analysis Services Server</span><span class="sxs-lookup"><span data-stu-id="60131-102">Disconnect Users and Sessions on Analysis Services Server</span></span>
  <span data-ttu-id="60131-103">Um administrador do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] talvez queira encerrar a atividade de usuário como parte do gerenciamento da carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60131-103">An administrator of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] may want to end user activity as part of workload management.</span></span> <span data-ttu-id="60131-104">Para fazer isso, cancele sessões e conexões.</span><span class="sxs-lookup"><span data-stu-id="60131-104">You do this by canceling sessions and connections.</span></span> <span data-ttu-id="60131-105">As sessões podem ser formadas automaticamente quando uma consulta é executada (implícito) ou nomeada no momento da criação pelo administrador (explícito).</span><span class="sxs-lookup"><span data-stu-id="60131-105">Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit).</span></span> <span data-ttu-id="60131-106">As conexões são canais abertos nos quais as consultas podem ser executadas.</span><span class="sxs-lookup"><span data-stu-id="60131-106">Connections are open conduits over which queries can be run.</span></span> <span data-ttu-id="60131-107">Tanto as sessões quanto as conexões podem ser encerradas enquanto estiverem ativas.</span><span class="sxs-lookup"><span data-stu-id="60131-107">Both sessions and connections can be ended while they are active.</span></span> <span data-ttu-id="60131-108">Por exemplo, o administrador pode encerrar o processamento de uma sessão caso o processamento esteja demorando muito ou se surgir alguma dúvida sobre a gravação do comando que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="60131-108">For example, an administrator may want to end processing for a session if the processing is taking too long or if some doubt has arisen as to whether the command being executed was written correctly.</span></span>  
  
## <a name="ending-sessions-and-connections"></a><span data-ttu-id="60131-109">Encerrando sessões e conexões</span><span class="sxs-lookup"><span data-stu-id="60131-109">Ending Sessions and Connections</span></span>  
 <span data-ttu-id="60131-110">Para gerenciar sessões e conexões, você pode usar DMVs (Exibições de gerenciamento dinâmico) e XMLA:</span><span class="sxs-lookup"><span data-stu-id="60131-110">To manage sessions and connections, you can use Dynamic Management Views (DMVs) and XMLA:</span></span>  
  
1.  <span data-ttu-id="60131-111">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="60131-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="60131-112">Cole qualquer uma das consultas de DMV a seguir em uma janela de consulta MDX para obter uma lista de todas as sessões, conexões e comandos que estão sendo executados no momento:</span><span class="sxs-lookup"><span data-stu-id="60131-112">Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:</span></span>  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  <span data-ttu-id="60131-113">Pressione F5 para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="60131-113">Press F5 to execute the query.</span></span>  
  
     <span data-ttu-id="60131-114">A consulta DMV retorna informações da sessão e da conexão em um conjunto de resultados de tabela que é mais fácil de ler e copiar.</span><span class="sxs-lookup"><span data-stu-id="60131-114">The DMV query returns session and connection information in a tabular result set that is easier read and copy from.</span></span>  
  
 <span data-ttu-id="60131-115">Mantenha a janela de consulta aberta.</span><span class="sxs-lookup"><span data-stu-id="60131-115">Keep the query window open.</span></span> <span data-ttu-id="60131-116">Na próxima etapa, você desejará retornar a esta página para copiar os SPIDs da sessão que deseja desconectar.</span><span class="sxs-lookup"><span data-stu-id="60131-116">In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.</span></span>  
  
 <span data-ttu-id="60131-117">Para encerrar uma sessão, abra uma segunda janela de consulta XMLA.</span><span class="sxs-lookup"><span data-stu-id="60131-117">To end a session, open a second XMLA query window.</span></span>  
  
1.  <span data-ttu-id="60131-118">Cole a sintaxe a seguir em uma janela de consulta MDX, substituindo o espaço reservado de ConnectionID, SessionID ou SPID por um valor válido copiado da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="60131-118">Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.</span></span>  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  <span data-ttu-id="60131-119">Pressione F5 para executar o comando cancelar.</span><span class="sxs-lookup"><span data-stu-id="60131-119">Press F5 to execute the cancel command.</span></span>  
  
 <span data-ttu-id="60131-120">O encerramento de uma conexão cancela todas as sessões e os SPIDs, fechando a sessão de host.</span><span class="sxs-lookup"><span data-stu-id="60131-120">Ending a connection cancels all sessions and SPIDs, closing the host session.</span></span>  
  
 <span data-ttu-id="60131-121">O encerramento de uma sessão interrompe todos os comandos (SPIDs) que estão sendo executados como parte da sessão em questão.</span><span class="sxs-lookup"><span data-stu-id="60131-121">Ending a session stops all commands (SPIDs) that are running as part of that session.</span></span>  
  
 <span data-ttu-id="60131-122">O encerramento de um SPID cancela um comando específico.</span><span class="sxs-lookup"><span data-stu-id="60131-122">Ending a SPID cancels a particular commend.</span></span>  
  
 <span data-ttu-id="60131-123">Em casos raros, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não fechará uma conexão se não puder acompanhar todas as sessões e os SPIDs associados à conexão (por exemplo, quando várias sessões estiverem abertas em um cenário HTTP).</span><span class="sxs-lookup"><span data-stu-id="60131-123">In rare cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will not close a connection if it cannot track all the sessions and SPIDs associated with the connection (for example, when multiple sessions are open in an HTTP scenario).</span></span>  
  
 <span data-ttu-id="60131-124">Para obter mais informações sobre o XMLA referenciado neste tópico, consulte [Executar método &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) e [Elemento Cancel &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="60131-124">For more information about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) and [Cancel Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60131-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60131-125">See Also</span></span>  
 <span data-ttu-id="60131-126">[Gerenciando conexões e sessões &#40;&#41;XMLA](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="60131-126">[Managing Connections and Sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span></span>  
 <span data-ttu-id="60131-127">[Elemento BeginSession &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="60131-127">[BeginSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span></span>  
 <span data-ttu-id="60131-128">[Elemento EndSession &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="60131-128">[EndSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span></span>  
 [<span data-ttu-id="60131-129">Elemento Session &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="60131-129">Session Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
