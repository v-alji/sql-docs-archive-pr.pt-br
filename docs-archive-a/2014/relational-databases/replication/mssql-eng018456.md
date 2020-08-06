---
title: MSSQL_ENG018456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018456 error
ms.assetid: 3daa8144-d81f-445a-b6c3-4bb3e9fd1526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b05ca549781215e0c4f247110fee87f6def56f04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681593"
---
# <a name="mssql_eng018456"></a><span data-ttu-id="10d66-102">MSSQL_ENG018456</span><span class="sxs-lookup"><span data-stu-id="10d66-102">MSSQL_ENG018456</span></span>
    
## <a name="message-details"></a><span data-ttu-id="10d66-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="10d66-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10d66-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="10d66-104">Product Name</span></span>|<span data-ttu-id="10d66-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="10d66-105">SQL Server</span></span>|  
|<span data-ttu-id="10d66-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="10d66-106">Event ID</span></span>|<span data-ttu-id="10d66-107">18456</span><span class="sxs-lookup"><span data-stu-id="10d66-107">18456</span></span>|  
|<span data-ttu-id="10d66-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="10d66-108">Event Source</span></span>|<span data-ttu-id="10d66-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="10d66-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="10d66-110">Componente</span><span class="sxs-lookup"><span data-stu-id="10d66-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="10d66-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="10d66-111">Symbolic Name</span></span>||  
|<span data-ttu-id="10d66-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="10d66-112">Message Text</span></span>|<span data-ttu-id="10d66-113">Falha no logon do usuário '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="10d66-113">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="10d66-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="10d66-114">Explanation</span></span>  
 <span data-ttu-id="10d66-115">O erro MSSQL_ENG018456 ocorre sempre que uma tentativa de logon falha.</span><span class="sxs-lookup"><span data-stu-id="10d66-115">Error MSSQL_ENG018456 is raised whenever a login attempt fails.</span></span> <span data-ttu-id="10d66-116">Se a mensagem de erro incluir a conta **distributor_admin** (Falha de logon para o usuário 'distributor_admin'.), o problema estará relacionado a uma conta usada pela replicação.</span><span class="sxs-lookup"><span data-stu-id="10d66-116">If the error message includes the account **distributor_admin** (Login failed for user 'distributor_admin'.), the issue is with an account used by replication.</span></span> <span data-ttu-id="10d66-117">A replicação cria um servidor remoto, **repl_distributor**, que permite a comunicação entre o Distribuidor e o Publicador.</span><span class="sxs-lookup"><span data-stu-id="10d66-117">Replication creates a remote server, **repl_distributor**, which allows communication between the Distributor and Publisher.</span></span> <span data-ttu-id="10d66-118">O logon **distributor_admin** é associado a esse servidor remoto e tem uma senha válida.</span><span class="sxs-lookup"><span data-stu-id="10d66-118">The login **distributor_admin** is associated with this remote server and must have a valid password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10d66-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="10d66-119">User Action</span></span>  
 <span data-ttu-id="10d66-120">Certifique-se de ter especificado uma senha para a conta.</span><span class="sxs-lookup"><span data-stu-id="10d66-120">Ensure that you have specified a password for this account.</span></span> <span data-ttu-id="10d66-121">Para obter mais informações, consulte [Proteger o Distribuidor](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="10d66-121">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d66-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10d66-122">See Also</span></span>  
 [<span data-ttu-id="10d66-123">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="10d66-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
