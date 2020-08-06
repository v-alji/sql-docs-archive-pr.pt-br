---
title: Cancelando comandos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 003c70362c38ae1838b4679abf6485fa031a9143
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679066"
---
# <a name="canceling-commands-xmla"></a><span data-ttu-id="8e25e-102">Cancelando comandos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="8e25e-102">Canceling Commands (XMLA)</span></span>
  <span data-ttu-id="8e25e-103">Dependendo das permissões administrativas do usuário que está emitindo o comando, o comando [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) no XML for Analysis (XMLA) pode cancelar um comando em uma sessão, uma sessão, uma conexão, um processo do servidor ou uma sessão ou conexão associada.</span><span class="sxs-lookup"><span data-stu-id="8e25e-103">Depending on the administrative permissions of the user issuing the command, the [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.</span></span>  
  
## <a name="canceling-commands"></a><span data-ttu-id="8e25e-104">Cancelando comandos</span><span class="sxs-lookup"><span data-stu-id="8e25e-104">Canceling Commands</span></span>  
 <span data-ttu-id="8e25e-105">Um usuário pode cancelar o comando em execução no contexto da sessão explícita atual ao enviar um comando `Cancel` sem propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="8e25e-105">A user can cancel the currently executing command within the context of the current explicit session by sending a `Cancel` command with no specified properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e25e-106">Um comando em execução em uma sessão implícita não poderá ser cancelado por um usuário.</span><span class="sxs-lookup"><span data-stu-id="8e25e-106">A command running in an implicit session cannot be canceled by a user.</span></span>  
  
### <a name="canceling-batch-commands"></a><span data-ttu-id="8e25e-107">Cancelando comandos em lote</span><span class="sxs-lookup"><span data-stu-id="8e25e-107">Canceling Batch Commands</span></span>  
 <span data-ttu-id="8e25e-108">Se um usuário cancelar um comando `Batch`, todos os comandos restantes ainda não executados no comando `Batch` serão cancelados.</span><span class="sxs-lookup"><span data-stu-id="8e25e-108">If a user cancels a `Batch` command, then all remaining commands not yet executed within the `Batch` command are canceled.</span></span> <span data-ttu-id="8e25e-109">Se o comando `Batch` for transacional, qualquer comando executado antes do comando `Cancel` será revertido.</span><span class="sxs-lookup"><span data-stu-id="8e25e-109">If the `Batch` command was transactional, any commands that were executed before the `Cancel` command runs are rolled back.</span></span>  
  
## <a name="canceling-sessions"></a><span data-ttu-id="8e25e-110">Cancelando sessões</span><span class="sxs-lookup"><span data-stu-id="8e25e-110">Canceling Sessions</span></span>  
 <span data-ttu-id="8e25e-111">Ao especificar um identificador de sessão para uma sessão explícita na propriedade [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) do `Cancel` comando, um administrador de banco de dados ou um administrador de servidor pode cancelar uma sessão, incluindo o comando atualmente em execução.</span><span class="sxs-lookup"><span data-stu-id="8e25e-111">By specifying a session identifier for an explicit session in the [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a database administrator or server administrator can cancel a session, including the currently executing command.</span></span> <span data-ttu-id="8e25e-112">Um administrador de banco de dados só poderá cancelar sessões para bancos de dados nos quais tiver permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="8e25e-112">A database administrator can only cancel sessions for databases on which he or she has administrative permissions.</span></span>  
  
 <span data-ttu-id="8e25e-113">Um administrador de banco de dados pode recuperar as sessões ativas para um banco de dados especificado recuperando o conjunto de linhas do esquema DISCOVER_SESSIONS.</span><span class="sxs-lookup"><span data-stu-id="8e25e-113">A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset.</span></span> <span data-ttu-id="8e25e-114">Para recuperar o conjunto de linhas de esquema DISCOVER_SESSIONS, o administrador de banco de dados usa o `Discover` método XMLA e especifica o identificador de banco de dados apropriado para a coluna de restrição SESSION_CURRENT_DATABASE na propriedade [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) do `Discover` método.</span><span class="sxs-lookup"><span data-stu-id="8e25e-114">To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA `Discover` method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) property of the `Discover` method.</span></span>  
  
## <a name="canceling-connections"></a><span data-ttu-id="8e25e-115">Cancelando conexões</span><span class="sxs-lookup"><span data-stu-id="8e25e-115">Canceling Connections</span></span>  
 <span data-ttu-id="8e25e-116">Ao especificar um identificador de conexão na propriedade [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) do `Cancel` comando, um administrador de servidor pode cancelar todas as sessões associadas a uma determinada conexão, incluindo todos os comandos em execução e cancelar a conexão.</span><span class="sxs-lookup"><span data-stu-id="8e25e-116">By specifying a connection identifier in the [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) property of the `Cancel` command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e25e-117">Se a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não puder localizar e cancelar as sessões associadas a uma conexão, como quando a bomba de dados abrir várias sessões ao fornecer conectividade http, a instância não poderá cancelar a conexão.</span><span class="sxs-lookup"><span data-stu-id="8e25e-117">If the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection.</span></span> <span data-ttu-id="8e25e-118">Se esse for o caso durante a execução de um comando `Cancel`, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="8e25e-118">If this case is encountered during the execution of a `Cancel` command, an error occurs.</span></span>  
  
 <span data-ttu-id="8e25e-119">Um administrador do servidor pode recuperar as conexões ativas para uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] recuperando o conjunto de linhas do esquema DISCOVER_CONNECTIONS que usa o método `Discover` XMLA.</span><span class="sxs-lookup"><span data-stu-id="8e25e-119">A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA `Discover` method.</span></span>  
  
## <a name="canceling-server-processes"></a><span data-ttu-id="8e25e-120">Cancelando processos do servidor</span><span class="sxs-lookup"><span data-stu-id="8e25e-120">Canceling Server Processes</span></span>  
 <span data-ttu-id="8e25e-121">Ao especificar um identificador de processo de servidor (SPID) na propriedade [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) do `Cancel` comando, um administrador de servidor pode cancelar os comandos associados a um determinado SPID.</span><span class="sxs-lookup"><span data-stu-id="8e25e-121">By specifying a server process identifier (SPID) in the [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a server administrator can cancel the commands associated with a given SPID.</span></span>  
  
## <a name="canceling-associated-sessions-and-connections"></a><span data-ttu-id="8e25e-122">Cancelando sessões e conexões associadas</span><span class="sxs-lookup"><span data-stu-id="8e25e-122">Canceling Associated Sessions and Connections</span></span>  
 <span data-ttu-id="8e25e-123">Você pode definir a propriedade [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) como true para cancelar as conexões, as sessões e os comandos associados à conexão, à sessão ou ao SPID especificados no `Cancel` comando.</span><span class="sxs-lookup"><span data-stu-id="8e25e-123">You can set the [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the `Cancel` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e25e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e25e-124">See Also</span></span>  
 <span data-ttu-id="8e25e-125">[Método Discover &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span><span class="sxs-lookup"><span data-stu-id="8e25e-125">[Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span></span>  
 [<span data-ttu-id="8e25e-126">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8e25e-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
